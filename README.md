# Project Title

DevOps Project: Hosting a Static HTML Web App on AWS

## Overview

This project involves deploying a static HTML web app on AWS using various services to achieve high availability, fault tolerance, and scalability. The resources and architecture are designed to provide a secure and reliable environment for hosting the web application.

## Architecture Overview

![Architecture Diagram](link_to_your_diagram_image)

 Key Components

1. VPC with Public and Private Subnets:**
   - The infrastructure is set up with a Virtual Private Cloud (VPC) consisting of public and private subnets across two availability zones to ensure high availability.

2. Internet Gateway:**
   - An Internet Gateway facilitates communication between instances in the VPC and the Internet.

3. Availability Zones:**
   - Two availability zones are utilized for high availability and fault tolerance.

4. Nat Gateway, Bastion Host, and ALB:**
   - Resources like Nat Gateway, Bastion Host, and Application Load Balancer (ALB) are deployed in public subnets for accessibility and load balancing.

5. EC2 Instance Connect Endpoint:**
   - EC2 Instance Connect Endpoint is used for secure SSH access to resources in both public and private subnets.

6. Private Subnets:**
   - Web servers and database servers are placed in private subnets for enhanced security.

7. Nat Gateway:**
   - The Nat Gateway enables instances in private subnets to access the internet.

8. EC2 Instances:**
   - EC2 instances are utilized to host the static HTML web application.

9. Application Load Balancer (ALB):**
   - ALB is employed to distribute web traffic across an Auto Scaling Group of EC2 instances in multiple availability zones.

10. Auto Scaling Group:**
    - Auto Scaling Group dynamically creates EC2 instances to ensure high availability, scalability, fault tolerance, and elasticity.

11. Route 53:**
    - Route 53 is used to register the domain name and create a record set for the web application.

12. **GitHub:**
    - GitHub is utilized to store and manage the web application files.

13. **AMI Creation:**
    - After the website is installed on the EC2 instance, the EC2 instance is used to create an Amazon Machine Image (AMI).

## Deployment Steps

1. Clone the GitHub repository with the web application files.
2. Set up a VPC with public and private subnets.
3. Deploy resources in public subnets: Internet Gateway, Nat Gateway, Bastion Host, ALB.
4. Deploy resources in private subnets: EC2 instances for web and database servers.
5. Configure Auto Scaling Group to ensure availability and scalability.
6. Use EC2 Instance Connect Endpoint for secure SSH access.
7. Register the domain using Route 53 and create a record set.
8. Install the web application on EC2 instances.
9. Create an AMI after successful installation.

## Additional Notes

- Ensure proper security group configurations for each resource.
- Regularly update and monitor the resources for security patches and performance optimization.
- Maintain backups and monitor logs for troubleshooting.

## Author

Jeffrey Egbagbe

## License

This project is licensed under the jeff_e License - see the [LICENSE.m](LICENSE.md) file for details.
