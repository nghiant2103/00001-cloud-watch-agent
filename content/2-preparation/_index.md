---
title : "Preparing VPC and EC2"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
You need to create 1 Linux instance on the public subnet to perform this lab.
{{% /notice %}}

Amazon Web Services (AWS) offers a comprehensive set of tools to build and manage cloud infrastructure. In this guide, we will walk through the process of creating a Virtual Private Cloud (VPC) with 1 public subnet, then launching an Amazon Elastic Compute Cloud (EC2) instance located in the public subnet within the VPC, creating an IAM (Identity and Access Management) role for EC2 to send data to Amazon CloudWatch.

The architecture overview after you complete this step will be as follows:

![VPC](/images/arc-cw-agent-preparation.png)

### Content

2.1. [Create VPC](2.1-create-vpc/)\
2.2. [Create public subnet](2.2-create-public-subnet/)\
2.3. [Create security group](2.3-create-sec-group/)\
2.4. [Create IAM role](2.4-create-iam-role/)\
2.5. [Create EC2 instance](2.5-create-ec2/)