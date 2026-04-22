# 📘 AWS ELB Tasks – Complete Implementation Guide

---

## 📌 Overview
This project demonstrates:
- Host-Based Routing using a single EC2 instance
- Path-Based Routing as an alternative
- Load Balancing across multiple EC2 instances using AWS Application Load Balancer (ALB)

---

# 🔹 Task 1: Host-Based Routing (Single EC2, Multiple Services)

## ✅ Objective
Configure an Application Load Balancer (ALB) to route traffic to multiple services running on a single EC2 instance using hostname.

---

## 🎯 Expected Outcome
- 1 EC2 instance
- 2 Nginx services on different ports
- ALB routes:
  - nginx1.example.com → Nginx-1  
  - nginx2.example.com → Nginx-2  
- Each hostname serves different content

---

## ⚙️ Implementation Steps

### 🔸 Step 1: Launch EC2
- Open ports: 22 (SSH), 80 (HTTP), 8081, 8082

---

### 🔸 Step 2: Install Nginx
```bash
sudo apt update -y
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
