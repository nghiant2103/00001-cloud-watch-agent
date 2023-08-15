---
title : "Create EC2 instance"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
  + Click **Instances**.
  + Click **Launch instances**.
  
![EC2](/images/2-preparation/2.5-create-ec2/001-createec2.png)

2. In the **Name** field, enter `Server`.

![EC2](/images/2-preparation/2.5-create-ec2/002-createec2.png)

2. On the **Application and OS Images (Amazon Machine Image)** section.
  + Click on **Amazon Machine Image (AMI)** drop-down list then select AMI **Amazon Linux 2 AMI**.
  
![EC2](/images/2-preparation/2.5-create-ec2/003-createec2.png)

3. On the **Instance Type** section.
 + Click on **Instance type** drop-down list then select **t2.micro**.
 
![EC2](/images/2-preparation/2.5-create-ec2/004-createec2.png)

4. On the **Key pair (login)** section.
  + Click on **Create new key pair**.

![EC2](/images/2-preparation/2.5-create-ec2/005-createec2.png)

  + In the **Key pair name** field, enter `server` then click on **Create key pair**.

![EC2](/images/2-preparation/2.5-create-ec2/006-createec2.png)

  + On click **Key pair name** drop-down list then select **server** key pair.

![EC2](/images/2-preparation/2.5-create-ec2/007-createec2.png)

5. On the **Network settings** section.

  + Click on **Edit**.

![EC2](/images/2-preparation/2.5-create-ec2/008-createec2.png)

  + Config the **Network settings**.

![EC2](/images/2-preparation/2.5-create-ec2/009-createec2.png)

6. On the **Advanced details** section.

  + In the **IAM instance profile** drop-down list select the **EC2CWAgentRole**.

![EC2](/images/2-preparation/2.5-create-ec2/010-createec2.png)

7. On the **Summary** section.
  + Click on **Launch instance**.

![EC2](/images/2-preparation/2.5-create-ec2/011-createec2.png)

The preparation of the VPC and EC2 instance for CloudWatch is now complete. Next step we will install and configuring Cloudwatch Agent in EC2 instance.