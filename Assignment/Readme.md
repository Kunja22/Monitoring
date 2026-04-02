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


