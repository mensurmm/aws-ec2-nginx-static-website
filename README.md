#AWS EC2 Static Website Deployment with Nginx
#Project Overview
This project demonstrates how to deploy a multi-page static website on a cloud server using AWS EC2 and Nginx.
The objective of this project is to gain hands-on experience with:
 	Cloud infrastructure deployment
 	Linux server management
 	Web server configuration
 	Static website hosting on the cloud
The website consists of multiple HTML pages with CSS styling and JavaScript functionality, hosted on an EC2 instance and served using Nginx.

#Architecture
The following diagram illustrates the architecture of the deployment.
 architecture-diagram.png
#Architecture Flow
1.	A user accesses the website through a web browser.
2.	The request travels through the public internet.
3.	The request reaches the AWS EC2 instance.
4.	Nginx processes the request.
5.	Nginx serves the static website files to the user.

#Website Features
The deployed website includes:
 	Multi-page navigation
 	Custom CSS styling
 	JavaScript functionality
 	Organized asset directories
 	Static content delivery through a web server

#Working of the project
#EC2 Instance Running
This screenshot shows the EC2 instance running in the AWS console with the public ip address of 34.241.240.103.
ec2-instance-running.png
 
#Security Group Configuration
The EC2 security group is configured to allow HTTP,HTTPS and also SSH  traffics  on their respective  port 80,443 and 22, enabling public access to the web server the https and the ssh are not mandatory but to avoid any flout.
 
security-group-rule.png
#Live Website
The website is accessible through the public IP address of the EC2 instance which is in the time of deployment  34.241.240.103 from the user browser as indicated on the diagram above (architecture-diagram.png).
  website-live.png

#Deployment Process
#1. Launch EC2 Instance
 	Created an EC2 instance
 	Selected Amazon Linux AMI
 	Generated a key pair for SSH access
 	Configured security group rules

#2. Configure Security Group
Enabled HTTP traffic by opening port 80.
Inbound rule configuration:
 	Type: HTTP
 	Protocol: TCP
 	Port: 80
 	Source: 0.0.0.0/0

#3. Connect to the Server Using SSH
ssh -i Web.pem ec2-user@ 34.241.240.103

#4. Install Nginx
Update the package manager and install the web server.
sudo yum update -y
sudo yum install nginx -y

#5. Start and Enable Nginx
sudo systemctl start nginx
sudo systemctl enable nginx

#6. Deploy Website Files
Copied the website files into the Nginx web directory.
/usr/share/nginx/html

#7. Access the Website
Open the public IP address of the EC2 instance in a browser:
http:// 34.241.240.103

#Skills Demonstrated
This project demonstrates practical experience in:
 	AWS cloud infrastructure deployment
 	Linux server administration
 	Web server configuration using Nginx
 	Secure server access via SSH
 	Static website hosting
 	GitHub project documentation

#Learning Outcomes
Through this project I learned how to:
 	Deploy and manage virtual servers in AWS
 	Configure security groups for network access
 	Install and configure a production web server
 	Host static websites on cloud infrastructure
 	Document technical projects professionally on GitHub

#Future Improvements
Possible enhancements for this project include:
 	Deploying the website using AWS S3 static hosting
 	Adding a Load Balancer
 	Implementing HTTPS with SSL certificates
 	Automating deployment with Infrastructure as Code
 	Integrating a CI/CD pipeline


