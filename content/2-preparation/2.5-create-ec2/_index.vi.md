---
title : "Tạo EC2 instance"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.5 </b> "
---

1. Truy cập [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
  + Click **Instances**.
  + Click **Launch instances**.
  
![EC2](/images/2-reparation/2.5-create-ec2/001-createec2.png)

2. Tại mục **Name**, nhập `Server`.

![EC2](/images/2-reparation/2.5-create-ec2/002-createec2.png)

2. Trong phần **Application and OS Images (Amazon Machine Image)**.
  + Click **Amazon Machine Image (AMI)** danh sách thả xuống sau đó chọn AMI **Amazon Linux 2 AMI**.
  
![EC2](/images/2-reparation/2.5-create-ec2/003-createec2.png)

3. Trong phần **Instance Type**.
 + Click **Instance type** danh sách thả xuống sau đó chọn **t2.micro**.
 
![EC2](/images/2-reparation/2.5-create-ec2/004-createec2.png)

4. Trong phần **Key pair (login)**.
  + Click **Create new key pair**.

![EC2](/images/2-reparation/2.5-create-ec2/005-createec2.png)

  + Tại mục **Key pair name**, nhập `server` rồi click **Create key pair**.

![EC2](/images/2-reparation/2.5-create-ec2/006-createec2.png)

  + Click **Key pair name** danh sách thả xuống sau đó chọn **server** key pair.

![EC2](/images/2-reparation/2.5-create-ec2/007-createec2.png)

5. Trong phần **Network settings**.

  + Click **Edit**.

![EC2](/images/2-reparation/2.5-create-ec2/008-createec2.png)

  + Cấu hình **Network settings**.

![EC2](/images/2-reparation/2.5-create-ec2/009-createec2.png)

6. Trong phần **Advanced details**.

  + Click **IAM instance profile** danh sách thả xuống sau đó chọn **EC2CWAgentRole**.

![EC2](/images/2-reparation/2.5-create-ec2/010-createec2.png)

7. Trong phần **Summary**.
  + Click **Launch instance**.

![EC2](/images/2-reparation/2.5-create-ec2/011-createec2.png)

Quá trình chuẩn bị VPC và EC2 instance cho CloudWatch hiện đã hoàn tất. Bước tiếp theo, chúng ta sẽ cài đặt và cấu hình Cloudwatch Agent trong EC2 instance.