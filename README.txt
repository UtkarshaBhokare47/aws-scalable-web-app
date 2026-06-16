# Scalable Web Application on AWS

## Project Overview

This project demonstrates how to build a scalable and highly available web application using AWS services.

## AWS Services Used

* Amazon EC2
* Application Load Balancer (ALB)
* Target Group
* Auto Scaling Group (ASG)
* Launch Template
* Amazon Machine Image (AMI)
* Security Groups

## Architecture

User
→ Application Load Balancer
→ Target Group
→ Multiple EC2 Instances
→ Apache Web Server

## Steps Performed

1. Created an EC2 instance
2. Installed Apache Web Server
3. Created a sample web page
4. Configured Security Groups
5. Created Target Group
6. Registered EC2 instance
7. Configured Application Load Balancer
8. Tested ALB routing
9. Created AMI
10. Created Launch Template
11. Created Auto Scaling Group
12. Configured scaling policy
13. Verified health checks

## Flow Diagram

                    Users
                      │
                      ▼
      Application Load Balancer (ALB)
                      │
                      ▼
           Target Group (HTTP:80)
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
   EC2 Instance1  EC2 Instance2  EC2 Instance3
    (Apache)       (Apache)       (Apache)
        │             │             │
        └─────────────┼─────────────┘
                      │
                 Web Response
                      │
                      ▼
                    Users

## Auto Scaling Flow


          AMI (web-app-ami)
                    │
                    ▼
      Launch Template
                    │
                    ▼
      Auto Scaling Group (ASG)
                    │
      ┌─────────────┴─────────────┐
      │                           │
CPU < 50%                  CPU > 50%
      │                           │
      ▼                           ▼
 Keep Existing           Launch New EC2
  Instances                 Instance
                                  │
                                  ▼
                    Register in Target Group
                                  │
                                  ▼
                ALB Starts Routing Traffic
                
                
## Complete Project Flow

Launch EC2
    │
    ▼
Install Apache
    │
    ▼
Create Web Page
    │
    ▼
Create Target Group
    │
    ▼
Register EC2
    │
    ▼
Create ALB
    │
    ▼
Attach Target Group
    │
    ▼
Test ALB DNS
    │
    ▼
Create AMI
    │
    ▼
Create Launch Template
    │
    ▼
Create Auto Scaling Group
    │
    ▼
Attach ALB + Target Group
    │
    ▼
Configure Scaling Policy
    │
    ▼
Health Checks Pass
    │
    ▼
Scalable Web App Ready ✅


## Outcome

Successfully built a scalable web application capable of distributing traffic across multiple EC2 instances using an Application Load Balancer and Auto Scaling Group.

