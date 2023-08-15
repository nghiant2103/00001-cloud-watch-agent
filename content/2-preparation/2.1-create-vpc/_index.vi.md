---
title : "Tạo VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---


#### Tạo VPC **cw-agent-vpc**
1. Truy cập [VPC service management console](https://console.aws.amazon.com/vpc/home)
   + Click **Your VPC**.
   + Click **Create VPC**.

![VPC](/images/2-preparation/2.1-create-vpc/001-createvpc.png)

2. Tại trang **Create VPC**.
   + Tại mục **Name tag**, nhập `cw-agent-vpc`.
   + Tại mục **IPv4 CIDR**, nhập `10.0.0.0/16`.
   + Click **Create VPC**.

![VPC](/images/2-preparation/2.1-create-vpc/002-createvpc.png)

Bước tiếp theo chúng ta sẽ tạo subnet trong VPC.