+++
title = "Clean up resources"
date = 2023
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

We will take the following steps to delete the resources we created in this exercise.

#### Delete EC2 instance

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
   + Click **Instances**.
   + Select both **Public Linux Instance** and **Private Windows Instance** instances.
   + Click **Instance state**.
   + Click **Terminate instance**, then click **Terminate** to confirm.

#### Delete IAM Role

2. Go to [IAM service management console](https://console.aws.amazon.com/iamv2/home#/home)
   + Click **Roles**.
   + In the search box, enter **SSM**.
   + Click to select **SSM-Role**.
   + Click **Delete**, then enter the role name **SSM-Role** and click **Delete** to delete the role.

![Clean](/images/6.clean/001-clean.png)

3. Click **Users**.
   + Click on user **Portfwd**.
   + Click **Delete**, then enter the user name **Portfwd** and click **Delete** to delete the user.


#### Delete VPC

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
   + Click **Your VPCs**.
   + Click on **Lab VPC**.
   + Click **Actions**.
   + Click **Delete VPC**.

2. In the confirm box, enter **delete** to confirm, click **Delete** to delete **Lab VPC** and related resources.

![Clean](/images/6.clean/006-clean.png)