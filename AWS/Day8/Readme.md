# AWS RDS (MySQL) Lab – Private Subnet Setup

This README documents a complete hands-on DevOps lab for setting up Amazon RDS (MySQL) in a private subnet and accessing it securely from an EC2 instance in a public subnet.

---

# 🧩 Lab Objectives

1. Create Amazon RDS (MySQL) in a private subnet  
2. Launch EC2 in a public subnet and connect using MySQL CLI  
3. Create multiple databases and separate users per database  
4. Test database access using different users  
5. Perform break/fix using Security Groups  
6. Take snapshot and modify instance type  

---

# 🏗️ Architecture Overview

- EC2 (Public Subnet) → used as client/bastion host  
- RDS MySQL (Private Subnet) → database layer  
- Security Groups → control network access  

---

# 🚀 Step 1: Create Amazon RDS (MySQL) in Private Subnet

### Steps:
- Go to AWS Console → RDS → Create Database  
- Engine: MySQL  
- Deployment: Standard Create  
- Connectivity:
  - VPC: same as EC2
  - Subnet group: Private subnet group
  - Public access: No  
- Security Group:
  - Allow port 3306 only from EC2 security group  
- Create database  

### Output:
- RDS endpoint (private)

---

# 💻 Step 2: Launch EC2 in Public Subnet

### Steps:
- Launch EC2 instance in public subnet  
- Attach Security Group:
  - SSH (22) → My IP  

### Install MySQL client:
```bash
sudo yum install mysql -y
