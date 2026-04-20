# AWS VPC Setup with Public & Private Subnets

## 📌 Objective
Create a custom VPC with:
- Public subnets (internet access via IGW)
- Private subnets (internet access via NAT Gateway)
- Deploy EC2 instances in both subnets
- Install and test Nginx

---

## 🏗️ Architecture Overview

- 1 VPC
- 1 Internet Gateway (IGW)
- 1 NAT Gateway
- 3 Public Subnets
- 3 Private Subnets
- Route Tables for Public & Private
- EC2 Instances:
  - 1 Public EC2
  - 1 Private EC2

---

## 🚀 Step 1: Create VPC

- Name: `Custom-VPC`
- CIDR Block: `10.0.0.0/16`
<img width="1919" height="790" alt="image" src="https://github.com/user-attachments/assets/bfeac524-0b25-40c0-8015-33ef49dc15f1" />


---

## 🌐 Step 2: Create Subnets

### Public Subnets:
- 10.0.1.0/24
- 10.0.2.0/24
- 10.0.3.0/24

### Private Subnets:
- 10.0.4.0/24
- 10.0.5.0/24
- 10.0.6.0/24

  <img width="1907" height="901" alt="image" src="https://github.com/user-attachments/assets/dddbce1e-ea44-473c-80e4-ccf24d8da76a" />


---

## 🌍 Step 3: Create Internet Gateway

- Create IGW
- Attach to VPC

<img width="1908" height="838" alt="image" src="https://github.com/user-attachments/assets/5b733327-77f0-4945-9f02-ce1a017f9d56" />
  

---

## 🔄 Step 4: Create NAT Gateway

- Create in **Public Subnet**
- Attach Elastic IP

---

## 🛣️ Step 5: Route Tables

### Public Route Table:
- Route:

  <img width="1917" height="825" alt="image" src="https://github.com/user-attachments/assets/b6ccedb7-9c22-4e2b-81cb-c79fd01cee9a" />

