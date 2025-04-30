# AWS Week 9 Assignment – ALB + ASG + S3

## Overview
This project demonstrates a highly available web application deployment using:
- Amazon S3 for static hosting
- EC2 instances with NGINX
- Auto Scaling Group
- Application Load Balancer (ALB)

---

## Part 1: S3 Static Website Hosting
- Created an S3 bucket: orjwan-clarusway
- Uploaded index.html, logo.png, and sda.png
- Enabled static website hosting
- Configured bucket policy for public access

*Website URL:*  
http://orjwan-clarusway.s3-website.eu-north-1.amazonaws.com

*Verification:*  
Using curl:http://orjwan-clarusway.s3-website.eu-north-1.amazonaws.com
---

## Part 2: Auto Scaling Group
- Created a Launch Template with user-data script to install nginx and pull index.html from S3
- Configured ASG with:
  - Min: 1, Max: 3, Desired: 2
  - Health checks for EC2 and ALB

---

## Part 3: Application Load Balancer
- Created internet-facing ALB with port 80 listener
- Target group mapped to ASG instances

*ALB DNS Name:*  
orjwan-alb-1583318478.eu-north-1.elb.amazonaws.com

---

## Final Results
- Website is accessible via S3 and ALB
- ASG replaces instances automatically
- All assets (HTML + logos) are served properly
- add documentation and deployment summary
