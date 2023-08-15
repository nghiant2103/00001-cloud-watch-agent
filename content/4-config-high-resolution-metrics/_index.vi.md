---
title : "Cấu hình phân giải cao"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : "<b>4. </b>"
---

Trường **metrics_collection_interval** chỉ định khoảng thời gian cho các metrics được thu thập, tính bằng giây. Bằng cách chỉ định giá trị nhỏ hơn 60 cho trường này, các metrics được thu thập dưới dạng **metrics phân giải cao**.

Ví dụ: nếu tất cả các metrics của bạn phải là **phân giải cao** và được thu thập **10 giây một lần**, hãy chỉ định **10** làm giá trị cho **metrics_collection_interval** trong phần **agent** dưới dạng tập hợp metrics toàn cầu.

```json
{
  "agent": {
    "metrics_collection_interval": 10
  }
}
```

Ngoài ra, ví dụ sau đặt cpu, ram và tất cả các số liệu khác sẽ được thu thập **cứ sau 10 giây**.

```json
{
  "agent": {
    "run_as_user": "cwagent",
    "metrics_collection_interval": 10
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
        "metrics_collection_interval": 10,
        "totalcpu": false
      },
      "mem": {
        "measurement": [
          "mem_used_percent"
        ],
        "metrics_collection_interval": 10
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

#### Cập nhật cấu hình CloudWatch Agent

1. Truy cập vào **AWS Systems Manager** rồi chọn **Parameter Store**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/001-config-high-resolution-metrics.png)

2. Click **AmazonCloudWatch-Agent-EC2-Configuration** parameter.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/002-config-high-resolution-metrics.png)

3. Click **Edit**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/003-config-high-resolution-metrics.png)

4. Nhập **Cấu hình phân giải cao** bên trên vào **Value**, rồi click **Save changes**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/004-config-high-resolution-metrics.png)

5. Tải lại và khởi động lại cấu hình CloudWatch Agent trong EC2 instance.

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c ssm:AmazonCloudWatch-Agent-EC2-Configuration
```

{{% notice warning %}}
Hãy nhớ rằng bất cứ khi nào bạn thay đổi cấu hình tác nhân trên **SSM Parameter Store**, bạn phải tìm nạp lại và khởi động lại cấu hình để các thay đổi có hiệu lực.
{{% /notice %}}

Sau khi đã định cấu hình thành công các metrics có độ phân giải cao, bước tiếp theo của chúng tôi là giám sát và phân tích các metrics này.