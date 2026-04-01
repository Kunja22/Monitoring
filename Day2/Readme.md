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
# Install prometheus and Grafana
<img width="1908" height="965" alt="image" src="https://github.com/user-attachments/assets/04404b40-11c8-4d74-a40a-4eb5b5eb2e14" />

# Prometheus yml file 
<img width="744" height="391" alt="image" src="https://github.com/user-attachments/assets/ac5fe172-3a8d-4613-a1ea-fcabf53e01ab" />

# Grafana.yml
<img width="1123" height="973" alt="image" src="https://github.com/user-attachments/assets/b43ed009-69b0-41a1-ba19-37db229c1d73" />

# Prometheus Dashboard
<img width="1919" height="1004" alt="image" src="https://github.com/user-attachments/assets/bd6ea37a-f82e-4708-90c4-6b34b6699591" />

# Gafana Dashboard
<img width="1908" height="1005" alt="image" src="https://github.com/user-attachments/assets/8edc4854-a730-4747-a62d-c027a1d5a11c" />



