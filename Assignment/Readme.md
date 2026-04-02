# 📦 Project Setup: Monitoring Stack with Docker Compose

## 📁 Project Structure

```
project/
│
├── app.js
├── Dockerfile
├── prometheus.yml
├── grafana/
├── docker-compose.yml
```
# 🚀 Task 2: Application Deployment with Metrics

● Deploy a sample application inside a container

● Ensure the application exposes metrics at a /metrics endpoint

● Validate that metrics are accessible via browser

🧩 Step 1: Create Sample Application (app.js)
 
 <img width="1138" height="970" alt="image" src="https://github.com/user-attachments/assets/f4943c73-f5d6-4095-a544-7de061910af9" />

 🐳 Step 2: Create Dockerfile
 
 <img width="855" height="717" alt="image" src="https://github.com/user-attachments/assets/b7fa5d4b-a3ac-470c-9239-a8df0e6859b5" />

 📦 Step 3: Build Docker Image
    
     docker build -t node-app .
▶️ Step 4: Run Container
       
      docker run -d -p 4000:4000 node-app

🌐 Step 5: Validate Application    
    <img width="1910" height="963" alt="image" src="https://github.com/user-attachments/assets/0450a768-ffcd-48b2-be63-10c7b23761c8" />

🔹 Task 3: Prometheus Configuration

 🧩 Step 1: Update prometheus.yml

 <img width="744" height="391" alt="image" src="https://github.com/user-attachments/assets/43c9f500-adfd-4d62-829a-6ccc957d0891" />

 
🐳 Step 2: Update docker-compose.yml

<img width="1177" height="986" alt="image" src="https://github.com/user-attachments/assets/12ccb879-35d0-40fd-b017-04d6cecbd7f1" />

▶️ Step 3: Restart Services

     docker-compose down
     docker-compose up --build

🌐 Step 4: Verify in Prometheus UI     
 <img width="1916" height="1003" alt="image" src="https://github.com/user-attachments/assets/6209a1d5-5a6d-4236-a4c2-289be35388b0" />

 🔹 Task 5: Grafana Setup
 <img width="1901" height="930" alt="image" src="https://github.com/user-attachments/assets/bc6d2176-c243-41ae-ace0-fa03a936cf7f" />

 🔹 Task 6: Infra Monitoring Dashboard
   <img width="1900" height="1003" alt="image" src="https://github.com/user-attachments/assets/3621d11f-8e29-4f7a-b99d-94d6890b59e2" />



 




