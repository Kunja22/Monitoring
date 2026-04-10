# 📊 ELK Stack Centralized Logging Setup

## 🚀 Overview

This project demonstrates a complete **centralized logging system** using the ELK Stack:

* Elasticsearch → Log storage & search
* Logstash → Log processing & enrichment
* Filebeat → Log shipper
* Kibana → Visualization & dashboards

  <img width="1908" height="878" alt="image" src="https://github.com/user-attachments/assets/1d260a3d-796d-40dc-947b-c0259166a435" />


  <img width="1226" height="802" alt="image" src="https://github.com/user-attachments/assets/e2c8657f-1abf-445a-b8b4-315696a2b77f" />

  <img width="1919" height="979" alt="image" src="https://github.com/user-attachments/assets/a5977bf9-f383-4110-8f0f-282537f828a3" />



A sample application continuously generates logs, which are collected, processed, and visualized.

---

## 🏗️ Architecture

```
Application → Filebeat → Logstash → Elasticsearch → Kibana
```

---

## 📦 Scope of Work

### 1. ELK Stack Setup

* Deployed using Docker Compose
* Includes:

  * Elasticsearch
  * Logstash
  * Kibana
  * Filebeat
* Runs with a single command

---

### 2. Sample Application

* A simple container generates logs continuously
* Logs stored in:

<img width="1878" height="974" alt="image" src="https://github.com/user-attachments/assets/5b624edf-9df6-4518-a935-31bd1ed31eb3" />

```
/var/log/app.log
```

---

### 3. Log Ingestion

* Filebeat reads logs from `/var/log/app.log`
* Sends logs to Logstash
* Logstash forwards logs to Elasticsearch
* Logs are visible in Kibana

<img width="1899" height="1005" alt="image" src="https://github.com/user-attachments/assets/e1b96c7a-82fc-448e-a186-43ecadca1036" />

---

### 4. Log Processing (Logstash)

* Logs enriched using filters
* Added custom fields:

  <img width="1893" height="858" alt="image" src="https://github.com/user-attachments/assets/55cd5f4f-6f7f-401e-87db-b7ec2a66b857" />


  * `service: log-generator`
  * `severity: INFO`

---

### 5. Kibana Exploration

* Created Data View:

```
logs-*
```

* Verified logs in **Discover**
* Applied filters:

```
service: log-generator
severity: ERROR
```

---

### 6. Dashboard

Created visualizations:

* 📊 Logs Over Time (line chart)
* 🔴 Error Count (metric)
* 🥧 Log Distribution (pie chart)

---

## ⚙️ Setup Instructions

### 1. Clone Repository

```bash
git clone <your-repo-url>
cd <repo-name>
```

### 2. Run ELK Stack

```bash
docker-compose up -d
```

### 3. Verify Containers

```bash
docker ps
```

### 4. Access Kibana

```
http://<your-ec2-ip>:5601
```

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── filebeat.yml
├── logstash/
│   └── logstash.conf
├── app/
│   └── log-generator
└── README.md
```

---

## 🔧 Key Decisions

### Why Filebeat?

* Lightweight log shipper
* Real-time log forwarding

### Why Logstash?

* Log parsing & enrichment
* Adding custom fields
* Scalable for future enhancements

---

## 📊 Usage

### View Logs

* Open Kibana → Discover
* Select data view:

```
logs-*
```

---

### Example Filters

Show logs for service:

```
service: log-generator
```

Show only error logs:

```
severity: ERROR
```

---

## 🧪 How to Test

1. Start the stack:

```bash
docker-compose up -d
```

2. Check logs generation:

```bash
tail -f /var/log/app.log
```

3. Open Kibana and verify logs in Discover

4. Apply filters and check dashboard

---

## 📸 Screenshots (Add in GitHub)

* Kibana Discover (logs visible)
* Dashboard (Logs Over Time, Error Count, Distribution)

---

## 🔥 Pull Request Details

### Title

```
feat: add ELK-based centralized logging setup
```

---

### Description

#### ✅ What was implemented

* ELK stack using Docker Compose
* Log generator application
* Filebeat log shipping
* Logstash processing & enrichment
* Kibana dashboards

---

#### 🧪 How to test

* Run `docker-compose up -d`
* Open Kibana
* Verify logs and dashboard

---




---
