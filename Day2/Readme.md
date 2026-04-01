# Prometheus
🔹 What is Prometheus?

Prometheus is an open-source monitoring and alerting tool designed for collecting and analyzing system and application metrics in real time.
It works by scraping metrics from configured targets (like servers, containers, or applications) at regular intervals and storing them in a time-series database.

🔹 Key Features
📊 Time-Series Data Storage – Stores metrics with timestamps for historical analysis
🔍 Powerful Query Language (PromQL) – Used to filter and analyze metrics
⚡ Pull-Based Monitoring – Collects data by scraping HTTP endpoints
🚨 Alerting System – Sends alerts based on defined conditions
📦 Integration Friendly – Works well with tools like Grafana, Kubernetes, Docker

🔹 Why Use Prometheus?
- Helps monitor system health and performance
- Detects issues before they become critical
- Provides real-time insights into infrastructure
- Widely used in DevOps and cloud-native environments

  🔹 Prometheus Architecture
  
       Targets → Exporters → Prometheus Server → TSDB
                                      ↓
                                   PromQL
                                      ↓
                               Alertmanager
                                      ↓
                                 Notifications

                    + Grafana (Dashboard Visualization)
