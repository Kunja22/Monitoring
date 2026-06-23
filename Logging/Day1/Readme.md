# 📄 Logging & Monitoring

## 🔹 Overview
This project implements **logging and monitoring** to ensure system reliability, performance tracking, and efficient debugging.

- **Logging** captures system events and errors  
- **Monitoring** tracks system performance using metrics  

---

# 🔹 Logging

## 📌 What is Logging?
Logging is the process of recording application events, errors, and system activity to help in debugging and monitoring.

---

## 🔹 Why Logging is Important
- Helps in debugging issues  
- Tracks application behavior  
- Captures errors and failures  
- Improves system visibility  
- Supports security and auditing  

---

## 🔹 Log Levels

The application uses the following log levels:

- **DEBUG** – Detailed debugging information  
- **INFO** – General application events  
- **WARN** – Unexpected but non-critical issues  
- **ERROR** – Application errors  
- **FATAL** – Critical failures  


---

## 🔹 Types of Logs

- Application Logs – Application events  
- System Logs – OS-level activity  
- Access Logs – Incoming requests  
- Error Logs – Failures and exceptions  
- Audit Logs – User actions (security)  
- Debug Logs – Developer-level details  
- Container Logs – Docker/Kubernetes logs  
- Infrastructure Logs – Cloud/system logs  

---

## 🔹 Real-Time Logging Example

### API Request Log
```json
{
  "timestamp": "2026-04-07T10:15:23Z",
  "level": "INFO",
  "message": "Incoming request",
  "method": "GET",
  "endpoint": "/api/users",
  "status": 200
}

## Monitoring vs Logging

Monitoring and logging are fundamental practices in modern application and infrastructure management. They work together to ensure system reliability, performance, and quick issue resolution.

### Key Differences

| Aspect        | Monitoring                                  | Logging                                      |
|---------------|----------------------------------------------|----------------------------------------------|
| Definition    | Tracks system performance using metrics      | Records detailed system events and messages  |
| Data Type     | Numerical data (CPU, memory, latency)        | Text or structured data (logs, JSON)         |
| Purpose       | Detect and alert on system health issues     | Diagnose and debug application issues        |
| Focus         | What is happening in the system              | Why it is happening                          |
| Alerts        | Built-in alerting based on thresholds        | Requires integration with alerting systems   |
| Output        | Dashboards and visual graphs                 | Log files or centralized log systems         |

---

