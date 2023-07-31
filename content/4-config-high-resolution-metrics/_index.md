---
title : "Config high resolution metrics"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

The **metrics_collection_interval** field specifies the time interval for the metrics collected, in seconds. By specifying a value of less than 60 for this field, the metrics are collected as **high-resolution metrics**.

For example, if your metrics should all be **high-resolution** and collected **every 10 seconds**, specify **10** as the value for **metrics_collection_interval** under the agent section as a global metrics collection interval.

```json
{
  "agent": {
    "metrics_collection_interval": 10
  }
}
```

Alternatively, the following example sets the cpu, ram, and all other metrics to be collected **every 10 second**.

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

#### Update CloudWatch Agent configuration

1. Navigate to **AWS Systems Manager** then choose **Parameter Store**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/001-config-high-resolution-metrics.png)

2. Click on **AmazonCloudWatch-Agent-EC2-Configuration** parameter.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/002-config-high-resolution-metrics.png)

3. Click on **Edit**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/003-config-high-resolution-metrics.png)

4. Enter the **high-resolution metric configuration** above into the **Value** field, then click on **Save changes**.

![Config high-resolution metrics](/images/4-config-high-resolution-metrics/004-config-high-resolution-metrics.png)

5. Refetch and restart CloudWatch Agent configuration in EC2 Instance.

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c ssm:AmazonCloudWatch-Agent-EC2-Configuration
```

{{% notice warning %}}
Remember that any time you change the agent configuration on **SSM Parameter Store**, you must refetch and restart the configuration to have the changes take effect.
{{% /notice %}}

Having successfully configured high-resolution metrics, our next step involves the monitoring and analysis of these metrics.