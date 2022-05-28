# Introduction

```sh
# Organization name
clouditech

# Workspace name
cloudbintech-workspace

```

# Set up
```sh
# Get token
terraform login

# token directory
/home/sharhan/.terraform.d/credentials.tfrc.json

# Add AWS CREDENTIALS as environment variables and mark them as sensitive on the terraform cloud console

# Before you run terraform init, do this
terraform login
terraform init
```

# Change infrastructure
```sh
# You can modify the infrastructure via CLI with variables
terrafrom apply -var="instance_type=t2.small"
```

# Use VCS-Driven Workflow
```sh

# This approach is to use your source control tool (eg; Github) to manage your terraform deployments 

# 1. First comment the cloud section of your versions.tf file
```
```tf
terraform {
/*
  cloud {
    organization = "clouditech"

    workspaces {
      name = "learn-terraform-cloud"
    }
  }
*/
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.28.0"
    }
  }

  required_version = ">= 0.14.0"
}
```

# terraform.auto.tfvars

```sh
# They inject environment variables to configuration. They are of lower precedence to Terraform Cloud set env variables
 
# 

```

## NB: When using the VCS-driven workflow for Terraform Cloud, you do not need to define the cloud block in your configuration.

