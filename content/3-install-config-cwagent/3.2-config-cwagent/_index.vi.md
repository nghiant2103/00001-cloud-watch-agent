---
title : "Cấu hình CloudWatch Agent"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : "<b>3.2. </b>"
---

#### 1. Tạo tệp cấu hình CloudWatch Agent

Tạo tệp cấu hình CloudWatch Agent sử dụng trình soạn thảo văn bản ưa thích của bạn.

```
sudo nano /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent.json
```

Dán cấu hình cơ bản sau vào file. Tùy chỉnh các metrics and logs bạn muốn thu thập bằng cách thêm hoặc sửa đổi metrics_collected và các phần khác. Tham khảo tài liệu về CloudWatch Agent để biết các tùy chọn cấu hình chi tiết.

```json
{
  "agent": {
    "run_as_user": "cwagent"
  },
  "metrics": {
    "namespace": "WorkshopCWAgent",
    "metrics_collected": {
      "cpu": {
        "resources": [
          "*"
        ],
        "measurement": [
          "cpu_usage_guest"
        ],
        "metrics_collection_interval": 60,
        "totalcpu": false
      },
      "mem": {
        "measurement": [
          "mem_used_percent"
        ],
        "metrics_collection_interval": 60
      }
    },
    "append_dimensions": {
      "ImageId": "${aws:ImageId}",
      "InstanceId": "${aws:InstanceId}",
      "InstanceType": "${aws:InstanceType}",
      "AutoScalingGroupName": "${aws:AutoScalingGroupName}"
    },
    "aggregation_dimensions": [
      [
        "InstanceId"
      ]
    ]
  }
}
```

#### 2. Lưu trữ file cấu hình trong AWS Systems Manager Parameter Store 

Parameter Store cho phép bạn lưu trữ dữ liệu cấu hình và ứng dụng một cách an toàn. 

1. Vào **AWS Systems Manager** rồi chọn **Parameter Store**.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/001-config-cwagent.png)

2. Click vào nút **Create parameter** để tạo một parameter mới.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/002-config-cwagent.png)

3. Cấu hình Parameter:

{{% notice note %}}
Tiền tố của tên parameter phải là 'AmazonCloudWatch-'.
{{% /notice %}}

+ Nhập tên cho parameter: `AmazonCloudWatch-Agent-EC2-Configuration`.
+ Thêm mô tả: `CloudWatch Agent configuration`.
+ Chọn bậc parameter **Standard**.
+ Đối với kiểu parameter chọn **String**.
+ Đối với kiểu dữ liệu, chọn **text**.
+ Nhập cấu hình json ở **phần 1** vào **Value**.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/003-config-cwagent.png)

+ Click **Create parameter**

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/004-config-cwagent.png)

#### 3. Áp dụng cấu hình

{{% notice note %}}
tùy chọn -s có nghĩa là khởi động lại Cloudwatch Agent sau khi định cấu hình cấu hình agent
{{% /notice %}}

+ File cấu hình trên máy cục bộ:

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c file:/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent.json
```

+ File cấu hình trên Systems Manager Parameter Store:

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c ssm:AmazonCloudWatch-Agent-EC2-Configuration
```

Sau khi cài đặt và định cấu hình CloudWatch Agent đã hoàn tất, chúng ta sẽ cấu hình các metric có độ phân giải cao trong bước tiếp theo.