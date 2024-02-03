![Alt Text][2.jpeg]
--
# Project Title

DevOps Project: Hosting a Static HTML Web App on AWS

## Overview

This project involves deploying a static HTML web app on AWS using various services to achieve high availability, fault tolerance, and scalability. The resources and architecture are designed to provide a secure and reliable environment for hosting the web application.

## Deployment Steps

### Deployment Bash Script

```bash
#!/bin/bash
sudo su
yum update -y
yum install -y httpd
cd /var/www/html
wget https://github.com/azeezsalu/jupiter/archive/refs/heads/main.zip
unzip main.zip
cp -r jupiter-main/* /var/www/html/
rm -rf jupiter-main main.zip
systemctl enable httpd 
systemctl start httpd
```

1. **VPC Configuration:**
   - Set up a VPC with public and private subnets across two availability zones for high availability and fault tolerance.
   - Use an Internet Gateway to allow communication between instances in the VPC and the Internet.
   - Place resources such as Nat Gateway, Bastion Host, and Application Load Balancer in public subnets.

2. **Security and Connectivity:**
   - Utilize the EC2 Instance Connect Endpoint for secure SSH access to resources in both public and private subnets.
   - Implement Nat Gateway to enable instances in private subnets to access the internet.

3. **Resource Placement:**
   - Deploy web servers and database servers in private subnets to enhance security.

4. **EC2 Instances and Application Load Balancer:**
   - Utilize EC2 instances to host the website and an Application Load Balancer to distribute web traffic across an Auto Scaling Group of EC2 instances in multiple availability zones.

5. **Auto Scaling Group:**
   - Set up Auto Scaling Group to dynamically create EC2 instances for high availability, scalability, fault tolerance, and elasticity.

6. **Domain Registration:**
   - Use Route 53 to register the domain name and create a record set for the web application.

7. **GitHub Repository:**
   - Store and manage web files using GitHub repository.

8. **AMI Creation:**
   - After the website is installed on the EC2 instance, create an Amazon Machine Image (AMI) for backup and scalability purposes.

## Additional Notes

- Ensure proper security group configurations for each resource to enhance security.
- Regularly update and monitor the resources for security patches and performance optimization.
- Maintain backups and monitor logs for troubleshooting.

## Author

Jeffrey Egbagbe
