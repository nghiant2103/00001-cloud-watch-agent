---
title : "Create security group"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : "<b>2.3 </b>"
---

In this step, we will proceed to create the security groups used for our instances. As you can see, these security groups will need to open traditional ports to **ssh** like port **22**.

#### Create security group for EC2 instance located in public subnet

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.
  + Click **Create security group**.

![SG](/images/2-preparation/2.3-create-sec-group/001-createsg.png)

3. In the **Security group name** field, enter `EC2ServerSG`. 
  + In the **Description** section, enter `Security group for EC2 instance`.
  + In the **VPC** section, click the **X** to reselect the **cw-agent-vpc** you created for this lab.

![SG](/images/2-preparation/2.3-create-sec-group/002-createsg.png)

4. Configure **Inbound rules**
  + In **Inbound rules**, click **Add rule**.
  + Select **Type: SSH** and **Source: My IP**. **My IP** represents 1 public IPv4 address you are using (will change when you change network).

![SG](/images/2-preparation/2.3-create-sec-group/003-createsg.png)

5. Keep **Outbound rule**, drag the mouse to the bottom.
  + Click **Create security group**.

![SG](/images/2-preparation/2.3-create-sec-group/004-createsg.png)

So we are done with creating the necessary security group for the EC2 instance.