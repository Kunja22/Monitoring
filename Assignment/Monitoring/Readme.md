# 📊 Monitoring Project (DevOps Assignment)

## 📌 Project Overview

This project demonstrates a complete monitoring setup using **Docker Compose**, including:

* Sample Application
* Prometheus (metrics collection)
* Grafana (visualization)
* Node Exporter (system metrics)

---

## 📁 Project Structure

```
monitoring-project/
│
├── app/                  # Application code
│   └── app.py
│
├── docker/               # Docker related files
│   └── Dockerfile
│
├── prometheus/           # Prometheus config
│   └── prometheus.yml
│
├── grafana/              # Grafana setup (optional provisioning)
│
├── docker-compose.yml    # Main orchestration file
│
└── README.md
```

---
✅ prometheus.yml

     Assignment/Monitoring/prometheus.yml

✅ docker-compose.yml     

    Assignment/Monitoring/docker-compose.yml
 
 Task 2: Application Deployment  
   
   <img width="1906" height="963" alt="image" src="https://github.com/user-attachments/assets/8c374bcd-1499-4538-8311-1d4ccc422d51" />

 ✅ Ensure the application exposes metrics at /metrics

<img width="1430" height="986" alt="image" src="https://github.com/user-attachments/assets/7153b806-1d38-4282-961a-2aebb9ee7f96" />

🔹 Task 3: Prometheus Integration

   <img width="1081" height="960" alt="image" src="https://github.com/user-attachments/assets/b3f2e456-49b6-43c0-b1fe-16dc33efc37b" />

   🔹 Task 4: Monitoring Stack Execution

     ## 🔹 Task 4: Monitoring Stack Execution

### 📌 Objective

Deploy all monitoring components using Docker Compose and ensure all services are accessible via browser.

---

### ⚙️ Services Included

* Application (Python App)
* Prometheus (Metrics Collection)
* Node Exporter (System Metrics)
* Grafana (Visualization)

---

### 🚀 Deployment Steps

#### 1️⃣ Start All Services

```bash
docker-compose down
docker-compose up -d --build
```

---

#### 2️⃣ Verify Running Containers

```bash
docker ps
```

Ensure the following containers are running:

* app
* prometheus
* node-exporter
* grafana

---

### 🌐 Access Services via Browser

Use your EC2 Public IP:

| Service       | URL                          |
| ------------- | ---------------------------- |
| Application   | http://<EC2-IP>:5000         |
| Metrics       | http://<EC2-IP>:5000/metrics |
| Prometheus    | http://<EC2-IP>:9090         |
| Node Exporter | http://<EC2-IP>:9100         |
| Grafana       | http://<EC2-IP>:3000         |

---

🔹 Task 5: Grafana Configuration
   
   <img width="1800" height="942" alt="image" src="https://github.com/user-attachments/assets/f4556e1c-ec6f-42b3-8f62-57c5abacafaf" />





 
