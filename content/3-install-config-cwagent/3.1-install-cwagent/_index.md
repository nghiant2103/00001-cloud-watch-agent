---
title : "Install CloudWatch Agent"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

#### 1. Connect to your EC2 Instance

Use the private key associated with your EC2 instance to connect via SSH. Replace your-ec2-instance-public-ip with the public IP address or DNS of your EC2 instance and your-private-key.pem with the path to your private key file:

```
ssh -i "your-private-key.pem" ec2-user@your-ec2-instance-public-ip
```

#### 2. Download the CloudWatch Agent

Update the package manager on your EC2 instance

```
sudo yum update -y
```

Download the CloudWatch Agent package using the following command:

```
sudo wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm
```

#### 3. Install the CloudWatch Agent

```
sudo rpm -U ./amazon-cloudwatch-agent.rpm
```

Next step we will configuring Cloudwatch Agent in EC2 instance.