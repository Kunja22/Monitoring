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

---

## 🌍 Step 3: Create Internet Gateway

- Create IGW
- Attach to VPC

---

## 🔄 Step 4: Create NAT Gateway

- Create in **Public Subnet**
- Attach Elastic IP

---

## 🛣️ Step 5: Route Tables

### Public Route Table:
- Route:
