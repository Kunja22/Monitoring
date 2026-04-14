# 🚀 AWS IAM User & S3 Bucket Setup (Using AWS CLI)

This project demonstrates how to:
- Create an IAM User  
- Assign least privilege permissions  
- Configure AWS CLI with IAM credentials  
- Create an S3 bucket using that IAM user  

---

## 📌 Prerequisites

- AWS Account  
- AWS CLI installed (`aws --version`)  
- Admin access (to create IAM user)  

---

## 🧑‍💻 Step 1: Create IAM User

### Using AWS Console:
1. Go to **IAM Dashboard**
2. Click **Users → Create User**
3. Enter username (e.g., `s3-user`)
4. Select:
   - ✅ **Programmatic access**
5. Click **Next**

---

## 🔐 Step 2: Assign Minimum Permissions

### ✅ Custom Policy (Least Privilege Recommended)

Create a policy:
