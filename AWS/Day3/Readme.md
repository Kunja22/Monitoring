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

<img width="1915" height="879" alt="image" src="https://github.com/user-attachments/assets/2271d833-25d2-444b-8adc-9115b8f29c37" />

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

<img width="1919" height="834" alt="image" src="https://github.com/user-attachments/assets/999660fd-9020-47ab-b52b-599316ed561c" />


---

### 5. Configure Security Group
- Allow SSH access:
  - Port: 22
  - Source: Anywhere (0.0.0.0/0)
- Default security group will be created automatically

  <img width="1906" height="813" alt="image" src="https://github.com/user-attachments/assets/83a12920-8ee4-4647-8140-998875ca7a97" />


---

### 6. Configure Storage
- Set root volume size to **20 GB**
- Volume type: General Purpose SSD (gp2/gp3)

<img width="1909" height="856" alt="image" src="https://github.com/user-attachments/assets/9c312956-1e5f-45e8-ab42-e7f3c5766dd3" />

---

### 7. Launch Instance
- Review all configurations
- Click **Launch Instance**

<img width="1904" height="839" alt="image" src="https://github.com/user-attachments/assets/d77f5783-6935-43ee-9a86-f2b55cafc2b5" />

---

# 🚀 EC2, S3 & Instance Profile

## 📌 Objective
To create an EC2 instance, connect via SSH, and upload files to an S3 bucket using AWS CLI, then verify the upload.

---

## 🛠️ Steps

### 1. Create EC2 Instance
- Go to AWS Management Console
- Navigate to EC2 Dashboard
- Click on **Launch Instance**
- Configure:
  - OS: Ubuntu (Latest LTS)
  - VPC: Default VPC
  - Enable **Auto-assign Public IP**
  - Instance Type: t2.micro
  - Key Pair: Create new `.pem` key pair
  - Security Group: Allow SSH (Port 22)
    <img width="1881" height="985" alt="image" src="https://github.com/user-attachments/assets/f4cf8195-2e61-4ae3-9c9d-84e0636bcce1" />
    
   - Create bucket using aws cli
     
    <img width="1919" height="973" alt="image" src="https://github.com/user-attachments/assets/a484c18a-f2b4-4ae5-b003-743dbd022904" />

    - Bucket show in S3

      <img width="1919" height="858" alt="image" src="https://github.com/user-attachments/assets/742fd089-70c3-4c58-a4a0-298b2531e736" />

    - File create

       <img width="1912" height="718" alt="image" src="https://github.com/user-attachments/assets/723dce1e-4c9c-4abc-bf63-4504c8ac5c16" />

    - File show on S3
 
      <img width="1906" height="851" alt="image" src="https://github.com/user-attachments/assets/160f0b94-2e10-461e-ad3e-779d6f9ca211" />



---

# 🚀 EC2 & User Data (Nginx Setup)

## 📌 Objective
To create an EC2 instance and use User Data to automatically install and start the Nginx web server, then access it via the public IP.

---

## 🛠️ Task 3

### 1. Create EC2 Instance


---

### 2. Add User Data Script

While launching the instance, scroll to **Advanced Details → User Data** and paste:

```bash
#!/bin/bash
sudo apt update -y
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

