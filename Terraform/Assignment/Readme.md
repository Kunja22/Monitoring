# Terraform AWS Infrastructure Deployment Using Modules

This project deploys AWS infrastructure using Terraform modules.

The infrastructure includes:

* VPC
* Subnet
* Security Group
* EC2 Instance
* S3 Bucket

Dynamic blocks are used for Security Group ingress rules.

---

# Project Structure

```text
terraform-aws/
│── main.tf
│── variables.tf
│── terraform.tfvars
│── provider.tf
│── README.md
│
├── modules/
│   ├── vpc/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   │
│   ├── subnet/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   │
│   ├── sg/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   │
│   ├── ec2/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   │
│   └── s3/
│       ├── main.tf
│       ├── variables.tf
│       └── outputs.tf
```

---

# Naming Convention

All resources follow the naming format:

```text
<prefix>-<name>-<env>-001
```

Examples:

```text
vpc-app-dev-001
subnet-app-dev-001
securitygroup-app-dev-001
ec2-app-dev-001
s3-app-dev-001
```

---

# Provider Configuration

## provider.tf

```hcl
provider "aws" {
  region = "us-east-1"
}
```

---

# Root Variables

## variables.tf

```hcl
variable "name" {
  default = "app"
}

variable "env" {
  default = "dev"
}

variable "vpc_cidr" {
  default = "10.0.0.0/16"
}

variable "subnet_cidr" {
  default = "10.0.1.0/24"
}

variable "sg_rules" {
  type = list(object({
    description = string
    from_port   = number
    to_port     = number
    protocol    = string
    cidr_blocks = list(string)
  }))

  default = [
    {
      description = "SSH"
      from_port   = 22
      to_port     = 22
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
    }
  ]
}
```

---

# Root Main Configuration

## main.tf

```hcl
module "vpc" {
  source = "./modules/vpc"

  vpc_name = "vpc-${var.name}-${var.env}-001"
  cidr     = var.vpc_cidr
}

module "subnet" {
  source = "./modules/subnet"

  subnet_name = "subnet-${var.name}-${var.env}-001"
  cidr        = var.subnet_cidr
  vpc_id      = module.vpc.vpc_id
}

module "sg" {
  source = "./modules/sg"

  sg_name = "securitygroup-${var.name}-${var.env}-001"
  vpc_id  = module.vpc.vpc_id

  sg_rules = var.sg_rules
}

module "ec2" {
  source = "./modules/ec2"

  ec2_name = "ec2-${var.name}-${var.env}-001"

  subnet_id         = module.subnet.subnet_id
  security_group_id = module.sg.sg_id
}

module "s3" {
  source = "./modules/s3"

  bucket_name = "s3-${var.name}-${var.env}-001"
}
```

---

# VPC Module

## modules/vpc/main.tf

```hcl
resource "aws_vpc" "this" {
  cidr_block = var.cidr

  tags = {
    Name = var.vpc_name
  }
}
```

## modules/vpc/variables.tf

```hcl
variable "vpc_name" {}
variable "cidr" {}
```

## modules/vpc/outputs.tf

```hcl
output "vpc_id" {
  value = aws_vpc.this.id
}
```

---

# Subnet Module

## modules/subnet/main.tf

```hcl
resource "aws_subnet" "this" {
  vpc_id            = var.vpc_id
  cidr_block        = var.cidr
  availability_zone = "us-east-1a"

  tags = {
    Name = var.subnet_name
  }
}
```

## modules/subnet/variables.tf

```hcl
variable "subnet_name" {}
variable "cidr" {}
variable "vpc_id" {}
```

## modules/subnet/outputs.tf

```hcl
output "subnet_id" {
  value = aws_subnet.this.id
}
```

---

# Security Group Module

## modules/sg/main.tf

```hcl
resource "aws_security_group" "this" {
  name   = var.sg_name
  vpc_id = var.vpc_id

  dynamic "ingress" {
    for_each = var.sg_rules

    content {
      description = ingress.value.description
      from_port   = ingress.value.from_port
      to_port     = ingress.value.to_port
      protocol    = ingress.value.protocol
      cidr_blocks = ingress.value.cidr_blocks
    }
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags = {
    Name = var.sg_name
  }
}
```

## modules/sg/variables.tf

```hcl
variable "sg_name" {}
variable "vpc_id" {}

variable "sg_rules" {
  type = list(object({
    description = string
    from_port   = number
    to_port     = number
    protocol    = string
    cidr_blocks = list(string)
  }))
}
```

## modules/sg/outputs.tf

```hcl
output "sg_id" {
  value = aws_security_group.this.id
}
```

---

# EC2 Module

## modules/ec2/main.tf

```hcl
resource "aws_instance" "this" {
  ami                    = "ami-0c02fb55956c7d316"
  instance_type          = "t2.micro"
  subnet_id              = var.subnet_id
  vpc_security_group_ids = [var.security_group_id]

  tags = {
    Name = var.ec2_name
  }
}
```

## modules/ec2/variables.tf

```hcl
variable "ec2_name" {}
variable "subnet_id" {}
variable "security_group_id" {}
```

## modules/ec2/outputs.tf

```hcl
output "instance_id" {
  value = aws_instance.this.id
}
```

---

# S3 Module

## modules/s3/main.tf

```hcl
resource "aws_s3_bucket" "this" {
  bucket = var.bucket_name

  tags = {
    Name = var.bucket_name
  }
}
```

## modules/s3/variables.tf

```hcl
variable "bucket_name" {}
```

---

# Terraform Commands

## Initialize Terraform

```bash
terraform init
```

## Validate Terraform

```bash
terraform validate
```

## Terraform Plan

```bash
terraform plan
```

## Deploy Infrastructure

```bash
terraform apply -auto-approve
```

---

# Verify Resources

Verify resources in AWS Console:

* VPC
* Subnet
* Security Group
* EC2 Instance
* S3 Bucket

AWS Region:

```text
us-east-1
```

---

# Destroy Infrastructure

```bash
terraform destroy -auto-approve
```

---

# Prerequisites

* Terraform Installed
* AWS CLI Configured
* IAM Role or AWS Credentials
* AWS Account Access

---

# Author

Terraform AWS Modular Infrastructure Project
