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
       1.Error Logs → shows errors
     
       2.Access Logs → user requests
     
       3.Debug Logs → detailed information
   
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

- Logz.io is a SaaS tool that collects logs, metrics, and traces to monitor and troubleshoot applications.
  # 🐧 Linux Monitoring & Logging Commands

## 📦 Monitoring Commands

### 🔹 System Monitoring
- `top` → Real-time CPU & memory usage  
- `htop` → Interactive system monitoring  
- `uptime` → System running time & load  

### 🔹 CPU Monitoring
- `mpstat` → CPU usage statistics  
- `lscpu` → CPU information  

### 🔹 Memory Monitoring
- `free -m` → Memory usage (in MB)  
- `vmstat` → Memory and CPU stats  

### 🔹 Disk Monitoring
- `df -h` → Disk space usage  
- `du -sh` → Directory size  
- `iostat` → Disk I/O performance  

### 🔹 Network Monitoring
- `netstat -tulnp` → Open ports and services  
- `ss -tulnp` → Modern alternative to netstat  
- `iftop` → Network bandwidth usage  
- `ping` → Check connectivity  

---

## 📦 Logging Commands

### 🔹 View Logs
- `cat /var/log/syslog` → View full logs  
- `less /var/log/syslog` → Scroll logs  
- `tail /var/log/syslog` → Last few lines  
- `tail -f /var/log/syslog` → Live logs  

### 🔹 Important Log Files
- `/var/log/syslog` → System logs  
- `/var/log/auth.log` → Authentication logs  
- `/var/log/nginx/access.log` → Web access logs  
- `/var/log/nginx/error.log` → Web error logs  

### 🔹 Search Logs
- `grep "error" /var/log/syslog` → Search for errors  
- `journalctl` → View systemd logs  
- `journalctl -u nginx` → Logs for specific service  

---
