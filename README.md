# AWS VPC with Subnets

## Description

This Terraform module creates an AWS Virtual Private Cloud (VPC) with public and private subnets. It also provisions an Internet Gateway and sets up route tables for public and private subnets.

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 1.3.0 |
| aws | ~> 4.0 |
| external | >= 2.2.0 |

## Providers

| Name | Version |
|------|---------|
| aws | ~> 4.0 |
| external | >= 2.2.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| project | Project name | `string` | - | yes |
| environment | Environment name | `string` | - | yes |
| name | Topic name | `string` | - | yes |
| sns_type | Valid values: fifo / standard | `string` | `standard` | no |

## Outputs

| Name | Description |
|------|-------------|
| sns_arn | The ARN of sns topic |

## Example Usage

```hcl
module "sns" {
  source      = "../../modules/sns"
  project     = my_project
  environment = my_environment
  name        = "cloudwatch-alarm"
  sns_type    = "standard"
}
```
