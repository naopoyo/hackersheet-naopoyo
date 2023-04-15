---
name: "Terraformのmoduleを使用してAWSのVPCを作成する"
slug: "rviftrj"
tags: ["AWS", "Terrafrom"]
---

# Terraformのmoduleを使用してAWSのVPCを作成する

以下のモジュールを使用してAWSのVPCを作成する。

- [terraform-aws-modules/vpc/aws | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
- [terraform-aws-modules/vpc/aws | vpc-endpoints Submodule | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest/submodules/vpc-endpoints)
- [terraform-aws-modules/security-group/aws | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/security-group/aws/1.19.0)


## locals

```terraform
data "aws_availability_zones" "available" {}

locals {
  app_name              = "app-name"
  region                = "us-east-1"
  vpc_name              = "${local.app_name}-vpc"
  vpc_endpoints_sg_name = "${local.app_name}-vpc-endpoints-sg"
  vpc_cidr              = "10.0.0.0/16"
  azs                   = slice(data.aws_availability_zones.available.names, 0, 3)
}
```


## VPC

```terraform
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"

  name = local.vpc_name
  cidr = local.vpc_cidr

  azs              = local.azs
  public_subnets   = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k)]
  private_subnets  = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k + 3)]
  database_subnets = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k + 6)]

  create_database_subnet_group = true

  # デフォルトセキュリティグループのルール削除
  manage_default_security_group  = true
  default_security_group_ingress = []
  default_security_group_egress  = []

  enable_dns_hostnames    = true
  enable_dns_support      = true
  enable_nat_gateway      = true
  single_nat_gateway      = true
  map_public_ip_on_launch = false
}
```


## VPC Endpoint

```terraform
module "vpc_endpoints" {
  source = "terraform-aws-modules/vpc/aws//modules/vpc-endpoints"

  vpc_id             = module.vpc.vpc_id
  security_group_ids = [module.vpc_endpoints_sg.security_group_id]

  endpoints = {
    s3 = {
      service = "s3"
      tags    = { Name = "${local.app_name}-vpce-s3" }
    },
    ecr_api = {
      service             = "ecr.api"
      private_dns_enabled = false
      subnet_ids          = module.vpc.private_subnets
      policy              = data.aws_iam_policy_document.generic_endpoint_policy.json
      tags                = { Name = "${local.app_name}-vpce-ecr-api" }
    },
    ecr_dkr = {
      service             = "ecr.dkr"
      private_dns_enabled = false
      subnet_ids          = module.vpc.private_subnets
      policy              = data.aws_iam_policy_document.generic_endpoint_policy.json
      tags                = { Name = "${local.app_name}-vpce-ecr-dkr" }
    },
  }
}
```

```terraform
data "aws_iam_policy_document" "generic_endpoint_policy" {
  statement {
    effect    = "Deny"
    actions   = ["*"]
    resources = ["*"]

    principals {
      type        = "*"
      identifiers = ["*"]
    }

    condition {
      test     = "StringNotEquals"
      variable = "aws:SourceVpc"

      values = [module.vpc.vpc_id]
    }
  }
}
```

```terraform
module "vpc_endpoints_sg" {
  source = "terraform-aws-modules/security-group/aws"

  name        = local.vpc_endpoints_sg_name
  description = "VPC endpoints security group"
  vpc_id      = module.vpc.vpc_id

  ingress_with_source_security_group_id = [
    {
      from_port                = 443
      to_port                  = 443
      protocol                 = "tcp"
      source_security_group_id = xxxxxx
    },
  ]

  egress_rules = ["all-all"]
}
```
