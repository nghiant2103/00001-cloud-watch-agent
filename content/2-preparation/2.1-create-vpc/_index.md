---
title : "Create VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---


#### Create VPC **cw-agent-vpc**
1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
   + Click **Your VPC**.
   + Click **Create VPC**.

![VPC](/images/2-preparation/2.1-create-vpc/001-createvpc.png)

2. At the **Create VPC** page.
   + In the **Name tag** field, enter `cw-agent-vpc`.
   + In the **IPv4 CIDR** field, enter `10.0.0.0/16`.
   + Click **Create VPC**.

![VPC](/images/2-preparation/2.1-create-vpc/002-createvpc.png)

Next step we will create the subnet in VPC.