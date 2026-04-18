🚀 Auto Scaling Group & Launch Template (Apache → Nginx)
📌 Objective
Launch multiple EC2 instances using Launch Template
Install Apache using user-data
Access web server via Public IP
Update Launch Template to use Nginx
Verify updated instances
🧱 Step 1: Create Launch Template (Apache)
Configuration:
AMI: Amazon Linux / Ubuntu
Instance Type: t3.micro
Key Pair: Existing or create new
Security Group:
SSH (22) → Your IP
HTTP (80) → 0.0.0.0/0
