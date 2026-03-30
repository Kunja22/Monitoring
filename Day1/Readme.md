# Day 1 Monitoring And Logging 
 # Oberservability 
   <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/65252cb7-ab5c-436f-b32e-a3e198e46bdd" />
Deffination  
   - Observability means understanding what is happening inside a system by looking at its data from outside.
   - It is the combination of Monitoring + Logging = Oberservability
  # 1.Monitoring    
   - Monitoring is the process of continuously tracking system health using metrics like CPU, memory, and performance.

  # Types of Monitoring
  🔹 1. Infrastructure Monitoring
     CPU usage
     Memory usage
     Disk space
     Example: EC2, VM health

🔹 2. Application Monitoring
     Response time
     Errors
     Requests
     Example: Website slow or fast

🔹 3. Network Monitoring
      Latency
      Packet loss
      Connectivity
      Example: Server not reachable

   # 2. logging
   - Logging means recording events or activities that happen inside a system.
    # Types of Logs
       Error Logs → shows errors
       Access Logs → user requests
       Debug Logs → detailed information
   
   # 3. Alerting 
   - Alerting means sending a notification when something goes wrong in the system.
   # 4. Tracing
   - Tracing means tracking the path of a request as it moves through different services.
   # Tools Overview
     # 📊 Observability Tools Overview

## 📦 Monitoring Tools

### 🔹 Open Source Tools
- Prometheus
- Grafana
- Nagios
- Zabbix
- Icinga

### 🔹 Closed Source Tools
- Datadog
- Dynatrace
- AppDynamics
- New Relic
- SolarWinds

---

## 📦 Logging Tools

### 🔹 Open Source Tools
- ELK Stack (Elasticsearch, Logstash, Kibana)
- Fluentd
- Graylog

### 🔹 Closed Source Tools
- Splunk
- Sumo Logic
- Datadog Logs
- Loggly
- Papertrail

---

## 📦 Tracing Tools

### 🔹 Open Source Tools
- Jaeger
- Zipkin
- OpenTelemetry
- Tempo (Grafana)

### 🔹 Closed Source Tools
- Datadog APM
- Dynatrace
- New Relic
- AppDynamics

---

## 📦 Visualization Tools

### 🔹 Open Source Tools
- Grafana
- Kibana
- Apache Superset
- Metabase

### 🔹 Closed Source Tools
- Datadog Dashboard
- New Relic Dashboard
- Dynatrace Dashboard
- Power BI

---

## 📦 Alerting Tools

### 🔹 Open Source Tools
- Prometheus Alertmanager
- Grafana Alerts
- Nagios Alerts
- Zabbix Alerts

### 🔹 Closed Source Tools
- PagerDuty
- Opsgenie
- VictorOps (Splunk On-Call)
- Datadog Alerts
