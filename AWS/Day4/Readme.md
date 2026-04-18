# 🚀 Launch Template Setup (Apache Web Server)

## 📌 Objective
Create a Launch Template in AWS that automatically installs Apache web server and displays a custom webpage.

---

## 🧱 Step 1: Create Launch Template

### Configuration:

- **AMI:** Amazon Linux / Ubuntu
 <img width="1916" height="806" alt="image" src="https://github.com/user-attachments/assets/8e27e00c-127f-4fcb-b58f-99bdbd1a91c8" />

- **Instance Type:** t3.micro  
- **Key Pair:** Create new or use existing `.pem` file  

### 🔐 Security Group Rules:
- Allow **SSH (Port 22)** → Your IP  
- Allow **HTTP (Port 80)** → Anywhere (0.0.0.0/0)  

---

## 🖥 User Data Script (Apache Installation)
<img width="1919" height="854" alt="image" src="https://github.com/user-attachments/assets/1bedf8de-bbc9-4641-a990-46fd0f633403" />


