---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : "<b>6. </b>"
---

We will take the following steps to delete the resources we created in this exercise.

#### Delete EC2 instance

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
   + Click **Instances**.
   + Select **server** instance.
   + Click **Instance state**.
   + Click **Terminate instance**, then click **Terminate** to confirm.

![Cleanup](/images/6-cleanup/001-cleanup.png)

#### Delete IAM Role

2. Go to [IAM service management console](https://console.aws.amazon.com/iamv2/home#/home)
   + Click **Roles**.
   + In the search box, enter `EC2CWAgentRole`.
   + Click to select **EC2CWAgentRole**.
   + Click **Delete**, then enter the role name **EC2CWAgentRole** and click **Delete** to delete the role.

![Cleanup](/images/6-cleanup/002-cleanup.png)

#### Delete VPC

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
   + Click **Your VPCs**.
   + Click on **cw-agent-vpc**.
   + Click **Actions**.
   + Click **Delete VPC**.

2. In the confirm box, enter **delete** to confirm, click **Delete** to delete **cw-agent-vpc** and related resources.

![Cleanup](/images/6-cleanup/003-cleanup.png)