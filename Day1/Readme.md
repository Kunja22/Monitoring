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
📦 Monitoring Tools
+----------------------+----------------------+
| Open Source          | Closed Source        |
+----------------------+----------------------+
| Prometheus           | Datadog              |
| Grafana              | Dynatrace            |
| Nagios               | AppDynamics          |
| Zabbix               | New Relic            |
| Icinga               | SolarWinds           |
+----------------------+----------------------+

📦 Logging Tools
+----------------------+----------------------+
| Open Source          | Closed Source        |
+----------------------+----------------------+
| ELK Stack            | Splunk               |
| Fluentd              | Sumo Logic           |
| Graylog              | Datadog Logs         |
|                      | Loggly               |
|                      | Papertrail           |
+----------------------+----------------------+

📦 Tracing Tools
+----------------------+----------------------+
| Open Source          | Closed Source        |
+----------------------+----------------------+
| Jaeger               | Datadog APM          |
| Zipkin               | Dynatrace            |
| OpenTelemetry        | New Relic            |
| Tempo (Grafana)      | AppDynamics          |
+----------------------+----------------------+

📦 Visualization Tools
+----------------------+----------------------+
| Open Source          | Closed Source        |
+----------------------+----------------------+
| Grafana              | Datadog Dashboard    |
| Kibana               | New Relic Dashboard  |
| Apache Superset      | Dynatrace Dashboard  |
| Metabase             | Power BI             |
+----------------------+----------------------+

📦 Alerting Tools
+----------------------+----------------------+
| Open Source          | Closed Source        |
+----------------------+----------------------+
| Alertmanager         | PagerDuty            |
| Grafana Alerts       | Opsgenie             |
| Nagios Alerts        | VictorOps            |
| Zabbix Alerts        | Datadog Alerts       |
+----------------------+----------------------+
     
