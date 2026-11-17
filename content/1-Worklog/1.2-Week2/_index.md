---
title: "Week 2 Worklog"
date: 2026-09-21
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Master basic AWS networking: VPC, subnets, Internet Gateway, route tables, security groups, and VPC Flow Logs.
* Practice deploying and managing Linux EC2 instances, snapshots, and AMIs.
* Get familiar with Cloud9 and basic Linux/AWS CLI commands.
* Deploy a static website with S3 and accelerate it with CloudFront.
* Create and manage a MySQL database on Amazon RDS and connect it to an application running on EC2.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - VPC:<br>&emsp;+ Create VPC<br>&emsp;+ Create Subnet: Public Subnet 1, Public Subnet 2, Private Subnet 1, Private Subnet 2<br>&emsp;+ Create Internet GateWay<br>&emsp;+ Create Route Table: Route table-Public<br>&emsp;+ Create Security Group: Public subnet - SG, Private subnet - SG, VPC-Endpoints-SG<br>&emsp;+ Enable VPC Flow Logs to view Flow Logs in CloudWatch<br>&emsp;                                                                                           | 21/09/2026 | 21/09/2026      | <https://000003.awsstudygroup.com/3-prerequisite/> |
| 3   | - EC2:<br>&emsp;+ Launch a Linux instance<br>&emsp;+ Remote instance control: MobaXterm, PuTTY<br>&emsp;+ Change instance type<br>&emsp;+ Create a snapshot<br>&emsp;+ Create and launch an AMI (image); | 22/09/2026   | 22/09/2026      | <https://000004.awsstudygroup.com/4-launchlinuxinstance/> |
| 4   | - Cloud9: <br>&emsp; + basic commands: pwd, ls -la, mkdir, cd, touch test.txt, vi test.txt, :wq, cat test.txt<br>&emsp;+ CLI: aws --version, aws s3 ls, aws ec2 describe-instances| 23/09/2026   | 23/09/2026      | <https://000049.awsstudygroup.com/1-createcloudshell/> |
| 5   | - S3 and Cloudfont:<br>&emsp;+ Create S3 bucket and upload data<br>&emsp;+ Enable static website hosting (at properties)<br>&emsp;+ Turn off: block all public access (at permission)<br>&emsp;+ ACLs enabled (at permission)<br>&emsp;+ Open S3 endpoint (at properties)<br>&emsp;+ Accelerate Static Websites with Cloudfront:<br>&emsp;  - Turn on: block all public access <br>&emsp;  - Cloudfront: create distribution, Enter index.html in the Default root object, copy policy in origin and paste at Bucket policy<br>&emsp;  - open Cloudfront endpoint<br>&emsp;                          | 24/09/2026 | 24/09/2026      | <https://000057.awsstudygroup.com/3-staticwebsite/> |
| 6   | - Aurora and RDS:<br>&emsp;+ create MySQL<br>&emsp;  + Launch EC2 instance<br>&emsp;+ Connect instance to MobaXterm<br>&emsp;+ Connect MySQL to MobaXterm<br>&emsp;+ Deploy the application<br>&emsp;+ interact dashboard MySQL (view, edit, delete)<br>&emsp;+ Maintenance & backups MySQL                                                                                      | 25/09/2026 | 25/09/2026      | <https://000005.awsstudygroup.com/3-create-rds/> |


### Week 2 Achievements:

* Created a VPC with 2 public and 2 private subnets, Internet Gateway, route table, and security groups (Public, Private, VPC Endpoints); enabled VPC Flow Logs to view in CloudWatch.
* Launched a Linux EC2 instance, controlled it remotely with MobaXterm/PuTTY, changed the instance type, and created a snapshot and an AMI.
* Used Cloud9 with basic Linux commands and the AWS CLI (aws --version, aws s3 ls, aws ec2 describe-instances).
* Created an S3 bucket, enabled static website hosting, and accelerated the website with a CloudFront distribution and bucket policy.
* Created a MySQL database on RDS, connected from EC2 via MobaXterm, deployed an application, manipulated data, and practiced maintenance and backups.
