Tasks for AutoScaling-Group & Launch Template
Launch multiple EC2 instances using Launch Template, where each instance is running a Web
Server (nginx or apache). Access the webpage of webserver.
1. Create a Launch Template with
a. AMI: Amazon Linux / Ubuntu
b. Instance Type: t3.micro
c. Key Pair: Create or use existing
d. Security Group:
Allow SSH (22)
Allow HTTP (80)
e. Add user-data to install Apache webserver
use custom index.html containing “Apache - Hello from Your Name!”.
2. Create Autoscaling-Group and use above Launch Template.
3. Increase instance count and access the webpage from new servers.
[ http://PublicIP:Port ]
4. ⚙ Update existing Launch Template (created above), remove apache user-data & add
nginx user data. Use custom index.html containing “Nginx - Hello from Your Name!”.
a. Update autoscaling-group to use this new Launch Template version.
b. Test whether Ec2 instances are showing Nginx webpage or not.
c. If not - then check the reason and fix the issue, your http://PublicIP:Port should
show “Nginx - Hello from Your Name!”
5. ✏ Document the complete step-by-step process in google docs with screenshots.
