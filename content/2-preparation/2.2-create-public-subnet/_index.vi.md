---
title : "Tạo public subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Tạo Public Subnet

1. Click **Subnets**.
  + Click **Create subnet**.

![VPC](/images/2-reparation/2.2-create-public-subnet/001-createsubnet.png)

2. Tại trang **Create subnet**.
  + Trong phần **VPC ID**, click **cw-agent-vpc**.
  + Tại mục **Subnet name**, nhập `cw-agent-public-subnet-01`.
  + Trong phần **Availability Zone**, chọn Availability zone đầu tiên.
  + Tại mục **IPv4 CIRD block** nhập `10.0.1.0/24`.

![VPC](/images/2-reparation/2.2-create-public-subnet/002-createsubnet.png)

3. Cuộn xuống dưới cùng, click **Create subnet**.

4. Click **cw-agent-public-subnet-01**.
  + Click **Actions**.
  + Click **Edit subnet settings**.

![VPC](/images/2-reparation/2.2-create-public-subnet/003-createsubnet.png)

5. Click **Enable auto-assign public IPv4 address**.
  + Click **Save**.

![VPC](/images/2-reparation/2.2-create-public-subnet/004-createsubnet.png)

6. Click **Internet Gateways**.
  + Click **Create internet gateway**.
  
![VPC](/images/2-reparation/2.2-create-public-subnet/005-createigw.png)

7. Tại trang **Create internet gateway**.
  + Tại mục **Name tag**, nhập `cw-agent-igw`.
  + Click **Create internet gateway**.
  
![VPC](/images/2-reparation/2.2-create-public-subnet/006-createigw.png)

8. Sau khi tạo thành công, click **Actions**.
  + Click **Attach to VPC**.
 
![VPC](/images/2-reparation/2.2-create-public-subnet/007-createigw.png)

9. Tại trang **Attach to VPC**.
  + Trong phần **Available VPCs**, chọn **cw-agent-vpc**.
  + Click **Attach internet gateway**.
  + Kiểm tra quá trình đính kèm thành công như hình bên dưới.

![VPC](/images/2-reparation/2.2-create-public-subnet/008-createigw.png)

10. Tiếp theo, chúng ta sẽ tạo một custom route table để gán cho **cw-agent-public-subnet-01**.
  + Click **Route Tables**.
  + Click **Create route table**.

![VPC](/images/2-reparation/2.2-create-public-subnet/009-creatertb.png)

11. Tại trang **Create route table**.
  + Tại mục **Name**, nhập `cw-agent-public-rtb`.
  + Trong phần **VPC**, chọn **cw-agent-vpc**.
  + Click **Create route table**.

12. Sau khi tạo route table thành công.
  + Click **Edit routes**.
  
![VPC](/images/2-reparation/2.2-create-public-subnet/010-creatertb.png)

13. Tại trang **Edit routes**.
  + Click **Add route**.
  + Tại mục **Destination**, nhập `0.0.0.0/0`
  + Trong phần **Target**, chọn **Internet Gateway** và chọn **cw-agent-igw**.
  + Click **Save changes**.

![VPC](/images/2-reparation/2.2-create-public-subnet/011-creatertb.png)

14. Click **Subnet associations** tab.
  + Click **Edit subnet associations** để  liên kết custom route table mà chúng ta vừa tạo trong **cw-agent-public-subnet-01**.


![VPC](/images/2-reparation/2.2-create-public-subnet/012-creatertb.png)

15. Tại trang **Edit subnet associations**.
  + Click **cw-agent-public-subnet-01**.
  + Click **Save associations**.

![VPC](/images/2-reparation/2.2-create-public-subnet/013-creatertb.png)

16. Kiểm tra xem thông tin route table đã được liên kết với **cw-agent-public-subnet-01** và thông tin định tuyến internet đã được trỏ tới Internet Gateway như minh họa bên dưới.

![VPC](/images/2-reparation/2.2-create-public-subnet/014-creatertb.png)

Bước tiếp theo chúng ta sẽ tạo security group cho EC2 instance.