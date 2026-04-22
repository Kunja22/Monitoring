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

---
## 🔸 Step 3: Configure Nginx Services
👉 Create two Nginx configuration files:
- `/etc/nginx/sites-available/nginx1` (port 8081)
- `/etc/nginx/sites-available/nginx2` (port 8082)

👉 Each config should:
- Listen on different ports (8081, 8082)
- Use different root directories
- Serve separate index.html pages

---

## 🔸 Step 4: Create Web Pages
👉 Create directories:
- `/usr/share/nginx/nginx1`
- `/usr/share/nginx/nginx2`

👉 Add custom HTML files:
- Nginx1 → "This is Nginx 1"
- Nginx2 → "This is Nginx 2"

---

## 🔸 Step 5: Enable Configurations
👉 Enable both configs:
- Link files from `sites-available` → `sites-enabled`

👉 Verify and restart Nginx:
- Check configuration using `nginx -t`
- Restart service using `systemctl restart nginx`

---
