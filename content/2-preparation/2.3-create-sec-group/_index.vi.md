---
title : "Tạo security group"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

Trong bước này, chúng ta sẽ tiến hành tạo security group được sử dụng cho các instances của chúng ta. Như bạn có thể thấy, những security group này sẽ cần mở các cổng truyền thống cho **ssh** như cổng **22**.

#### Tạo security group cho EC2 instance nằm trong public subnet

1. Truy cập [VPC service management console](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.
  + Click **Create security group**.

![SG](/images/2-reparation/2.3-create-sec-group/001-createsg.png)

3. Tại mục **Security group name**, nhập `EC2ServerSG`. 
  + Trong phần **Description**, nhập `Security group for EC2 instance`.
  + Trong phần **VPC**, click **X** rồi chọn **cw-agent-vpc** bạn đã tạo cho bài lab này.

![SG](/images/2-reparation/2.3-create-sec-group/002-createsg.png)

4. Cấu hình **Inbound rules**
  + Trong **Inbound rules**, click **Add rule**.
  + Chọn **Type: SSH** và **Source: My IP**. **My IP** đại diện cho 1 địa chỉ IPv4 công khai mà bạn đang sử dụng (sẽ thay đổi khi bạn thay đổi mạng).

![SG](/images/2-reparation/2.3-create-sec-group/003-createsg.png)

5. Giữ **Outbound rule**, cuộn xuống dưới.
  + Click **Create security group**.

![SG](/images/2-reparation/2.3-create-sec-group/004-createsg.png)

Vậy là chúng ta đã hoàn thành việc tạo security group cần thiết cho EC2 instance.