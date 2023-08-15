---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Create IAM Role

In this step, we will proceed to create IAM Role. In this IAM Role, the policy **AmazonSSMManagedInstanceCore** will be assigned, this is the policy that allows the EC2 server to communicate with the Session Manager to save the configuration of CloudWatch Agent.

1. Go to [IAM service administration interface](https://console.aws.amazon.com/iamv2/)

2. In the left navigation bar, click **Roles**, then click **Create role**.

![role](/images/2-preparation/2.4-create-iam-role/001-create-iam-role.png)

4. Click **AWS service**, then click **EC2**, and then click **Next**.

![role](/images/2-preparation/2.4-create-iam-role/002-create-iam-role.png)

5. In the Search box, enter `CloudWatchAgentAdminPolicy` and press Enter to search for this policy.
  + Click the policy **CloudWatchAgentAdminPolicy**.
  + Click **Next**

![role](/images/2-preparation/2.4-create-iam-role/003-create-iam-role.png)

6. Name the Role `EC2CWAgentRole` in Role Name.

![role](/images/2-preparation/2.4-create-iam-role/004-create-iam-role.png)

7. Click **Create Role**.

![role](/images/2-preparation/2.4-create-iam-role/005-create-iam-role.png)

So we are done with creating the necessary IAM role for the EC2 instance.