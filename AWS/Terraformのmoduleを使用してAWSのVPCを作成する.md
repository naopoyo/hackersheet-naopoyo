---
name: "Terraformのmoduleを使用してAWSにVPCを作成する"
slug: "rviftrj"
emoji: "🤖"
tags: ["AWS", "Terraform"]
---

# Terraformのmoduleを使用してAWSにVPCを作成する

以下のモジュールを使用してAWSのVPCを作成する。ECSをプライベートなサブネットで実行する場合のために、VPCエンドポイントも作成する。

- [terraform-aws-modules/vpc/aws | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
- [terraform-aws-modules/vpc/aws | vpc-endpoints Submodule | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest/submodules/vpc-endpoints)
- [terraform-aws-modules/security-group/aws | Terraform Registry](https://registry.terraform.io/modules/terraform-aws-modules/security-group/aws/1.19.0)



## locals

```terraform
data "aws_availability_zones" "available" {}

locals {
  app_name              = "example-app"
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
  azs  = local.azs

  public_subnets   = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k)]
  private_subnets  = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k + 3)]
  database_subnets = [for k, v in local.azs : cidrsubnet(local.vpc_cidr, 8, k + 6)]

  # DBサブネットグループを作成
  create_database_subnet_group = true

  # デフォルトセキュリティグループのルール削除
  manage_default_security_group  = true
  default_security_group_ingress = []
  default_security_group_egress  = []

  # https://docs.aws.amazon.com/ja_jp/vpc/latest/userguide/vpc-dns.html#vpc-dns-support
  enable_dns_hostnames = true
  enable_dns_support   = true

  # NATゲートウェイを作成
  enable_nat_gateway = true

  # すべてのプライベートネットワークで単一の共有 NATゲートウェイをプロビジョニングする場合は、true。
  single_nat_gateway = true

  # サブネットで起動されたインスタンスがパブリック IPv4 アドレスを受け取るかどうかを示します。デフォルト値は false。
  map_public_ip_on_launch = false
}
```

### VPC作成の補足

- [VPC の DNS 属性 - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/ja_jp/vpc/latest/userguide/vpc-dns.html#vpc-dns-support)
  - **enable_dns_hostnames**
    - VPC がパブリック IP アドレスを持つインスタンスへのパブリック DNS ホスト名の割り当てをサポートするかどうかを決定します。
  - **enable_dns_support**
    - VPC が Amazon 提供の DNS サーバーを介した DNS 解決策をサポートするかどうかを決定します。

## VPC Endpoint

S3のGatewayエンドポイント、ecr.apiとecr.dkrのエンドポイントを作成。

```terraform
module "vpc_endpoints" {
  source = "terraform-aws-modules/vpc/aws//modules/vpc-endpoints"

  vpc_id             = module.vpc.vpc_id
  security_group_ids = [module.vpc_endpoints_sg.security_group_id]

  endpoints = {
    s3 = {
      service_type = "Gateway"
      service      = "s3"
      route_table_ids = concat(
        module.vpc.public_route_table_ids,
        module.vpc.private_route_table_ids
      )
      tags = { Name = "${local.app_name}-vpce-s3" }
    },
    ecr_api = {
      service             = "ecr.api"
      private_dns_enabled = true
      subnet_ids          = module.vpc.private_subnets
      policy              = data.aws_iam_policy_document.generic_endpoint_policy.json
      tags                = { Name = "${local.app_name}-vpce-ecr-api" }
    },
    ecr_dkr = {
      service             = "ecr.dkr"
      private_dns_enabled = true
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
    effect    = "Allow"
    actions   = ["*"]
    resources = ["*"]

    principals {
      type        = "*"
      identifiers = ["*"]
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

  ingress_with_cidr_blocks = [
    {
      from_port   = 443
      to_port     = 443
      protocol    = "tcp"
      cidr_blocks = module.vpc.vpc_cidr_block
    },
  ]

  egress_rules = ["all-all"]
}
```
