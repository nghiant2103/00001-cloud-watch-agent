---
title : "Dọn dẹp tài nguyên"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : "<b>6. </b>"
---

Chúng ta sẽ thực hiện các bước sau để xóa các tài nguyên mà chúng ta đã tạo trong bài lab này.

#### Xóa EC2 instance

1. Truy cập [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
   + Click **Instances**.
   + Chọn **server** instance.
   + Click **Instance state**.
   + Click **Terminate instance**, rồi click **Terminate** để xác nhận.

![Cleanup](/images/6-cleanup/001-cleanup.png)

#### Xóa IAM Role

2. Truy cập [IAM service management console](https://console.aws.amazon.com/iamv2/home#/home)
   + Click **Roles**.
   + Trong search box, nhập `EC2CWAgentRole`.
   + Click để chọn **EC2CWAgentRole**.
   + Click **Delete**, rồi nhập role name **EC2CWAgentRole** và click **Delete** để xóa role.

![Cleanup](/images/6-cleanup/002-cleanup.png)

#### Xóa VPC

1. Truy cập [VPC service management console](https://console.aws.amazon.com/vpc/home)
   + Click **Your VPCs**.
   + Click **cw-agent-vpc**.
   + Click **Actions**.
   + Click **Delete VPC**.

2. Trong hộp xác nhận, nhập **delete** để xác nhận, nhấp vào **Delete** để xóa **cw-agent-vpc** và các tài nguyên liên quan.
![Cleanup](/images/6-cleanup/003-cleanup.png)