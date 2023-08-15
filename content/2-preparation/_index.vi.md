---
title : "Chuẩn bị VPC và EC2"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>2. </b>"
---

{{% notice info %}}
Bạn cần tạo 1 Linux instance trên public subnet để thực hiện bài lab này.
{{% /notice %}}

Amazon Web Services (AWS) offers a comprehensive set of tools to build and manage cloud infrastructure. In this guide, we will walk through the process of creating a Virtual Private Cloud (VPC) with 1 public subnet, then launching an Amazon Elastic Compute Cloud (EC2) instance located in the public subnet within the VPC, creating an IAM (Identity and Access Management) role for EC2 to send data to Amazon CloudWatch.

The architecture overview after you complete this step will be as follows:

Amazon Web Services (AWS) cung cấp một bộ công cụ toàn diện để xây dựng và quản lý cơ sở hạ tầng đám mây. Trong hướng dẫn này, chúng ta sẽ hướng dẫn qua quy trình tạo một Mạng Riêng Ảo (VPC) với 1 public subnet, sau đó khởi chạy một thể hiện Amazon Elastic Compute Cloud (EC2) nằm trong public subnet trong VPC, tạo một IAM role (Quản lý danh tính và Truy cập) cho EC2 để gửi dữ liệu đến Amazon CloudWatch.

Tổng quan kiến trúc sau khi bạn hoàn thành bước này sẽ như sau:

![VPC](/images/arc-cw-agent-preparation.png)

### Nội dung

2.1. [Tạo VPC](2.1-create-vpc/)\
2.2. [Tạo public subnet](2.2-create-public-subnet/)\
2.3. [Tạo security group](2.3-create-sec-group/)\
2.4. [Tạo IAM role](2.4-create-iam-role/)\
2.5. [Tạo EC2 instance](2.5-create-ec2/)