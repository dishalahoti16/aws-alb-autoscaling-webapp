# Highly Available Web App — ALB & Auto Scaling Group

## Project Overview
Deployed a highly available, fault-tolerant web application on AWS using Application Load Balancer and Auto Scaling Group across multiple Availability Zones. The system automatically scales EC2 instances based on traffic load.

## Architecture
Internet → ALB (Multi-AZ) → Auto Scaling Group
                              ↓            ↓
                          EC2 (AZ-1)   EC2 (AZ-2)
                                  ↓
                         SNS Alert on Scale Event

## AWS Services Used
- Application Load Balancer (ALB)
- Auto Scaling Group + Launch Template
- EC2 (Web server instances)
- SNS (Scaling event notifications)
- Target Groups + Health Checks

## What I Built
- Launch Template with AMI, instance type, and user data script
- Auto Scaling Group spanning 2 AZs with min=1, max=3, desired=2
- ALB with Target Group and HTTP health checks
- Scale-out policy triggered at 70% CPU utilization
- SNS notification on every scaling event

## Key Learnings
- Difference between ALB, NLB, and CLB
- Launch Template vs Launch Configuration
- Health check grace period and its importance
- Sticky sessions and connection draining

## Certification
AWS Certified Solutions Architect – Associate (SAA-C03)
