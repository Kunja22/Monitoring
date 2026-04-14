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

<img width="1900" height="899" alt="image" src="https://github.com/user-attachments/assets/d863d6db-71b3-458e-89fa-684a2fa3739f" />

2. Click **Users → Create User**

<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/a01b7484-e3b2-4f02-9eb0-81abc75053c3" />

5. Enter username (e.g., `s3-user`)
6. Select:
   - ✅ **Programmatic access**
7. Click **Next**

---

## 🔐 Step 2: Assign Minimum Permissions

### ✅ Custom Policy (Least Privilege Recommended)

Create a policy:
