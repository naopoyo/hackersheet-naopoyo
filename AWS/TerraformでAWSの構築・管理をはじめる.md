---
name: "TerraformでAWSの構築・管理をはじめる"
slug: "rhbveyg"
tags: ["AWS", "Terraform"]
---

# TerraformでAWSの構築・管理をはじめる

## IAMユーザーの作成

AWSのコンソールでTerraform実行用のIAMユーザーを作成して、アクセスキーとシークレットキーを控えておく。

### IAMユーザーのポリシー設定

以下のポリシーでこのサンプルは動く。

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:*"
            ],
            "Resource": "*"
        }
    ]
}
```

## HomebrewでTerraformとAWS CLIをインストール

```
brew install terraform awscli
```

## Terraform用のディレクトリとファイルを作成

```
mkdir example-terraform && cd $_ && touch main.tf secrets.tfvars .gitignore
```

上記コマンドを実行後、各ファイルを以下のように編集する。

### main.tf

```terraform
variable "aws_access_key" {}
variable "aws_secret_key" {}

locals {
  app_name = "example-app"
  region   = "us-east-1"
}

provider "aws" {
  region = local.region
  access_key = var.aws_access_key
  secret_key = var.aws_secret_key

  # 全てのリソースに共通のタグをつける
  default_tags {
    tags = {
      env      = "production"
      app-name = local.app_name
    }
  }
}

# S3のバケットを作成する
resource "aws_s3_bucket" "example" {
  bucket = "example-bucket"
}
```

### secrets.tfvars

```terraform
aws_access_key = "XXXX"
aws_secret_key = "XXXX"
```

`XXXX`にはアクセスキーとシークレットキーを設定する。

### .gitignore

参考: [gitignore/Terraform.gitignore at main · github/gitignore](https://github.com/github/gitignore/blob/main/Terraform.gitignore)

```
# Local .terraform directories
**/.terraform/*

# .tfstate files
*.tfstate
*.tfstate.*

# Crash log files
crash.log
crash.*.log

# Exclude all .tfvars files, which are likely to contain sensitive data, such as
# password, private keys, and other secrets. These should not be part of version 
# control as they are data points which are potentially sensitive and subject 
# to change depending on the environment.
*.tfvars
*.tfvars.json

# Ignore override files as they are usually used to override resources locally and so
# are not checked in
override.tf
override.tf.json
*_override.tf
*_override.tf.json

# Include override files you do wish to add to version control using negated pattern
# !example_override.tf

# Include tfplan files to ignore the plan output of command: terraform plan -out=tfplan
# example: *tfplan*

# Ignore CLI configuration files
.terraformrc
terraform.rc
```

## terraform init

```
terraform init
```

上記コマンドを実行すると、`.terraform、`と`.terraform.lock.hcl`が作成される。

## terraform plan

```
terraform plan -var-file=secrets.tfvars
```

上記コマンドを実行後に以下のように表示されたら成功🎉

```
Terraform used the selected providers to generate the following execution plan. Resource actions are indicated
with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_s3_bucket.example will be created

...
...
...

Plan: 1 to add, 0 to change, 0 to destroy.
```