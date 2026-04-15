# 🚀 EC2 Instance Setup (Ubuntu)

## 📌 Objective
To create an Amazon EC2 instance using Ubuntu OS in the default VPC with Public IP enabled, SSH key pair, default security group, and 20GB root volume.

---

## 🛠️ Configuration Details

| Parameter            | Value                          |
|---------------------|--------------------------------|
| OS                  | Ubuntu (Latest LTS)           |
| VPC                 | Default VPC                   |
| Public IP           | Enabled                       |
| Key Pair            | New SSH Key Pair (.pem)       |
| Security Group      | Default (Auto-created)        |
| Storage (Root)      | 20 GB                         |
| Instance Type       | t2.micro (Free Tier)          |

---

## 📋 Steps to Create EC2 Instance

### 1. Launch Instance
- Open AWS Management Console
- Navigate to EC2 Dashboard
- Click on **Launch Instance**

---

### 2. Select AMI
- Choose **Ubuntu Server (Latest LTS version)**

---

### 3. Configure Instance
- Select instance type (`t2.micro`)
- Choose **Default VPC**
- Enable **Auto-assign Public IP**

---

### 4. Create Key Pair
- Click **Create new key pair**
- Name: `my-keypair`
- Type: RSA
- Format: `.pem`
- Download and store securely

---

### 5. Configure Security Group
- Allow SSH access:
  - Port: 22
  - Source: Anywhere (0.0.0.0/0)
- Default security group will be created automatically

---

### 6. Configure Storage
- Set root volume size to **20 GB**
- Volume type: General Purpose SSD (gp2/gp3)

---

### 7. Launch Instance
- Review all configurations
- Click **Launch Instance**

---

## ✅ Outcome
- EC2 instance created successfully
- Ubuntu OS installed
- Public IP enabled for remote access
- SSH key pair generated
- Security group configured
- Root volume set to 20GB

---

## 🔐 Connect to EC2 Instance

```bash
chmod 400 my-keypair.pem
ssh -i my-keypair.pem ubuntu@<Public-IP>
