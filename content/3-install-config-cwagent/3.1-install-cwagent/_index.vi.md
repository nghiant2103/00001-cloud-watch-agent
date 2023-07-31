---
title : "Cài đặt CloudWatch Agent"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

#### 1. Kết nối đến EC2 Instance

Sử dụng khóa riêng được liên kết với EC2 instance của bạn để kết nối qua SSH. Thay your-ec2-instance-public-ip bằng địa chỉ IP công cộng hoặc DNS của phiên bản EC2 và your-private-key.pem bằng đường dẫn đến tệp khóa riêng của bạn:

```
ssh -i "your-private-key.pem" ec2-user@your-ec2-instance-public-ip
```

#### 2. Tải gói CloudWatch Agent

Cập nhật trình quản lý gói trên EC2 instance của bạn

```
sudo yum update -y
```

Tải xuống gói CloudWatch Agent bằng lệnh sau:

```
sudo wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm
```

#### 3. Cài đặt CloudWatch Agent

```
sudo rpm -U ./amazon-cloudwatch-agent.rpm
```

Bước tiếp theo, chúng ta sẽ cấu hình Cloudwatch Agent trong EC2 instance.