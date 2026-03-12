AWS EC2 Static Website Deployment with Nginx
Project Overview
This project demonstrates how to deploy a multi-page static website on a cloud server using AWS EC2 and Nginx.

Objectives:

Cloud infrastructure deployment
Linux server management
Web server configuration
Static website hosting on the cloud
The website consists of multiple HTML pages with CSS styling and JavaScript functionality, hosted on an EC2 instance and served using Nginx.

Architecture
![Architecture Diagram](architecture-diagram.png)

Architecture Flow:

User accesses the website through a web browser.
The request travels through the public internet.
The request reaches the AWS EC2 instance.
Nginx processes the request.
Nginx serves the static website files to the user.
Website Features
Multi-page navigation
Custom CSS styling
JavaScript functionality
Organized asset directories
Static content delivery through a web server
EC2 Instance Running
![EC2 Instance Running](ec2-instance-running.png)
EC2 instance running in the AWS console with public IP address: 34.241.240.103

Security Group Configuration
![Security Group Rule](security-group-rule.png)
Configured to allow HTTP (80), HTTPS (443), and SSH (22) traffic. HTTPS and SSH are not required for basic access but can provide security.

Live Website
![Website Live](website-live.png)
Website accessible through the public IP address (34.241.240.103) from a user browser.

Deployment Process
1. Launch EC2 Instance

Create an EC2 instance (Amazon Linux AMI)
Generate a key pair for SSH access
Configure security group rules
2. Configure Security Group Open port 80 for HTTP traffic:

Code
Type:    HTTP
Protocol: TCP
Port:    80
Source:  0.0.0.0/0
3. Connect to the Server Using SSH

bash
ssh -i Web.pem ec2-user@34.241.240.103
4. Install Nginx

bash
sudo yum update -y
sudo yum install nginx -y
5. Start and Enable Nginx

bash
sudo systemctl start nginx
sudo systemctl enable nginx
6. Deploy Website Files

Copy website files into the Nginx web directory:
bash
/usr/share/nginx/html
7. Access the Website

Open the EC2 instance public IP in your browser:
Code
http://34.241.240.103
Skills Demonstrated
AWS cloud infrastructure deployment
Linux server administration
Web server configuration with Nginx
Secure server access via SSH
Static website hosting
Professional project documentation on GitHub
Learning Outcomes
Deploy and manage virtual servers in AWS
Configure security groups for network access
Install and configure production web servers
Host static websites on cloud infrastructure
Document technical projects on GitHub
Future Improvements
Deploying the website using AWS S3 static hosting
Adding a load balancer
Implementing HTTPS with SSL certificates
Automating deployment with Infrastructure as Code
Integrating a CI/CD pipeline
