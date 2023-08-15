---
title : "Tạo IAM Role"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Tạo IAM Role

Ở bước này, chúng ta sẽ tiến hành tạo IAM Role. Trong IAM Role này, policy **AmazonSSMManagedInstanceCore** sẽ được chỉ định, đây là policy cho phép máy chủ EC2 giao tiếp với Session Manager để lưu cấu hình của CloudWatch Agent.

1. Truy cập [IAM service administration interface](https://console.aws.amazon.com/iamv2/)

2. Trong thanh điều hướng bên trái, click **Roles**, rồi click **Create role**.

![role](/images/2-preparation/2.4-create-iam-role/001-create-iam-role.png)

4. Click **AWS service**, rồi click **EC2**, và sau đó click **Next**.

![role](/images/2-preparation/2.4-create-iam-role/002-create-iam-role.png)

5. Trong Search box, nhập `CloudWatchAgentAdminPolicy` và nhấn Enter để tìm kiếm policy này.
  + Click policy **CloudWatchAgentAdminPolicy**.
  + Click **Next**

![role](/images/2-preparation/2.4-create-iam-role/003-create-iam-role.png)

6. Nhâp `EC2CWAgentRole` trong mục Role Name.

![role](/images/2-preparation/2.4-create-iam-role/004-create-iam-role.png)

7. Click **Create Role**.

![role](/images/2-preparation/2.4-create-iam-role/005-create-iam-role.png)

Vậy là chúng ta đã hoàn tất việc tạo IAM role cần thiết cho EC2 instance.