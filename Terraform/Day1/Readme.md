# Terraform Hands-on Practice

## Overview

This project demonstrates basic Terraform operations including:

- Installing Terraform
- Creating and destroying resources
- Managing AWS resources
- Understanding Terraform plan and refresh
- Exploring important Terraform commands

---

# 1. Install Terraform on Ubuntu

## Update System Packages

```bash
sudo apt update
sudo apt install -y gnupg software-properties-common curl lsb-release
```

## Add HashiCorp GPG Key

```bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | \
sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
```

## Add HashiCorp Repository

```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com noble main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

## Install Terraform

```bash
sudo apt update
sudo apt install terraform
```

## Verify Installation

```bash
terraform -version
```
<img width="1913" height="965" alt="image" src="https://github.com/user-attachments/assets/53bf1be7-1830-4660-9ee5-40f92e9dcb90" />


---

# 2. Create Terraform Project

## Create Directory

```bash
mkdir terraform-demo
cd terraform-demo
```

---

# 3. Create Terraform Configuration

Create a file named `main.tf`

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "demo_server" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t2.micro"

  tags = {
    Name = "TerraformDemo"
  }
}
```

---

# 4. Initialize Terraform

```bash
terraform init
```

<img width="1913" height="972" alt="image" src="https://github.com/user-attachments/assets/826163a0-eaae-4f45-a08a-fd95b43d9a65" />


### Purpose

- Downloads AWS provider plugins
- Initializes Terraform working directory

---

# 5. Check Terraform Plan

```bash
terraform plan
```

<img width="1917" height="970" alt="image" src="https://github.com/user-attachments/assets/9a31459d-ef27-43f4-bedf-a3d3caba8f18" />


### Purpose

Terraform compares:

- Current infrastructure
- Terraform configuration

It shows what changes will happen before applying.

---

# 6. Apply Terraform Configuration

```bash
terraform apply
```

Type:

```bash
yes
```

<img width="1917" height="955" alt="image" src="https://github.com/user-attachments/assets/876c26bf-67e4-4995-84b9-9c84e83cfcd4" />

### Result

Terraform creates the EC2 instance in AWS.

---

# 7. Verify Created Resource

Check AWS Console:

- EC2 Dashboard
- Running Instances

You should see:

```text
Hello world
```

<img width="1892" height="862" alt="image" src="https://github.com/user-attachments/assets/59f5fbd1-c204-4b05-81ba-2b36a75f42df" />

---

# 8. Destroy Infrastructure

```bash
terraform destroy
```

Type:

```bash
yes
```

<img width="1906" height="1007" alt="image" src="https://github.com/user-attachments/assets/7765f3a6-9d5f-43b4-bf3b-fec149b5e56f" />


### Result

Terraform removes all created resources.

---

# 9. Add Another Resource

Update `main.tf`

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "demo_server" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t2.micro"

  tags = {
    Name = "TerraformDemo"
  }
}

resource "aws_s3_bucket" "demo_bucket" {
  bucket = "terraform-demo-bucket-123456"

  tags = {
    Name = "TerraformBucket"
  }
}
```

---

# 10. Run Terraform Plan Again

```bash
terraform plan
```

### Output

Terraform shows:

- Existing EC2 instance unchanged
- New S3 bucket will be created

---

# 11. Apply New Changes

```bash
terraform apply
```

### Result

Terraform creates only the new S3 bucket.

---

# 12. Modify Existing Resource

Change instance type:

```hcl
instance_type = "t3.micro"
```

Run:

```bash
terraform plan
```

### Observation

Terraform detects infrastructure drift/change.

Apply changes:

```bash
terraform apply
```

---

# 14. Terraform Refresh

## Command

```bash
terraform refresh
```

<img width="1917" height="937" alt="image" src="https://github.com/user-attachments/assets/d7d38bf4-69c2-4042-b9f1-649eb527dc7d" />

## Purpose

Terraform refresh updates the local Terraform state file using real cloud infrastructure information.

### Example

If someone manually changes an EC2 instance in AWS Console:

- Terraform state becomes outdated
- `terraform refresh` syncs state with real infrastructure

---

# Difference Between Terraform Plan and Refresh

| Terraform Plan | Terraform Refresh |
|----------------|------------------|
| Shows upcoming changes | Syncs Terraform state |
| Compares config vs state | Compares real infra vs state |
| Does not update state automatically | Updates state file |
| Used before apply | Used for synchronization |

---

# 14. Important Terraform Commands

---

## Terraform Validate

Checks configuration syntax.

```bash
terraform validate
```

### Example Output

```text
Success! The configuration is valid.
```

---

## Terraform Format

Formats Terraform files properly.

```bash
terraform fmt
```

---

## Terraform Show

Displays Terraform state details.

```bash
terraform show
```

---

## Terraform State

Used to inspect Terraform state.

### List Resources

```bash
terraform state list
```

### Show Specific Resource

```bash
terraform state show aws_instance.demo_server
```

---

# 15. Important Terraform Files

| File/Folder | Purpose |
|-------------|----------|
| main.tf | Main Terraform configuration |
| terraform.tfstate | Stores infrastructure state |
| terraform.tfstate.backup | Backup state |
| .terraform/ | Provider plugins |
| variables.tf | Input variables |
| outputs.tf | Output values |

---

# 16. Terraform Workflow

```text
Write Configuration
        ↓
terraform init
        ↓
terraform validate
        ↓
terraform plan
        ↓
terraform apply
        ↓
terraform destroy
```

---

# 17. Best Practices

- Always run `terraform plan` before apply
- Store state files securely
- Avoid hardcoding secrets
- Use Git for version control
- Use remote backend for teams
- Use modules for reusable code

---

# 18. Conclusion

This hands-on Terraform practice covered:

- Terraform installation
- Alias configuration
- Infrastructure deployment
- Infrastructure destruction
- Adding new resources
- Updating resources
- Understanding Terraform refresh
- Exploring essential Terraform commands

Terraform simplifies Infrastructure as Code (IaC) and automates cloud resource management efficiently.
