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

3. Permission

<img width="1814" height="793" alt="image" src="https://github.com/user-attachments/assets/54164d01-1da3-4193-98e5-8d392d9321c4" />


4. Create Bucket
   
<img width="1887" height="810" alt="image" src="https://github.com/user-attachments/assets/e0b759db-074e-4572-a1be-eefbc45de776" />

5.Create bucket on CLI

<img width="1902" height="968" alt="image" src="https://github.com/user-attachments/assets/9320ba4e-d74f-4067-b459-fe7d178b6e08" />


---
#  Task 2 AWS IAM Role - Delete S3 Bucket Using IAM Role

## 📌 Objective
Create an IAM Role with minimum required permissions and use it to delete an existing S3 bucket securely.

---

## 🛠️ Prerequisites
- AWS Account
- IAM user/role with permission to create IAM roles
- AWS CLI installed and configured OR AWS Console access
- Existing S3 bucket

---

## 🚀 Steps to Complete the Task

## 1. Create IAM Role

Go to:
**AWS Console → IAM → Roles → Create Role**

Select:
- Trusted entity type: AWS service (or as per requirement)

---

## 2. Attach Permission Policy (Least Privilege)

Create a custom policy and attach it to the role.

### 📄 IAM Policy (S3 Delete Access Only)





