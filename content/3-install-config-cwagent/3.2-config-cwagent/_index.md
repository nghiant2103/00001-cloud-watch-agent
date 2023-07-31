---
title : "Config CloudWatch Agent"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

{{% notice info %}}
If you saved the configuration file on the local computer, enter the following command. Replace configuration-file-path with the path to the agent configuration file. This file is called config.json if you created it with the wizard, and might be called amazon-cloudwatch-agent.json if you created it manually.
{{% /notice %}}

#### 1. Create the CloudWatch Agent configuration file

Create the CloudWatch Agent configuration file using your preferred text editor.

```
sudo nano /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent.json
```

Paste the following basic configuration into the file. Customize the metrics and logs you want to collect by adding or modifying the metrics_collected, and other sections. Refer to the CloudWatch Agent documentation for detailed configuration options.

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

#### 2. Store configuration file in AWS Systems Manager Parameter Store 

Parameter Store allows you to securely store configuration and application data. 

1. Navigate to **AWS Systems Manager** then choose **Parameter Store**.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/001-config-cwagent.png)

2. Click on the **Create parameter** button to create a new parameter.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/002-config-cwagent.png)

3. Configure Parameter:

{{% notice note %}}
The prefix of parameter name must be 'AmazonCloudWatch-'.
{{% /notice %}}

+ Enter a name for the parameter: `AmazonCloudWatch-Agent-EC2-Configuration`.
+ Add description: `CloudWatch Agent configuration`.
+ Choose the **Standard** parameter tier.
+ For the parameter type, select **String**.
+ For the data type, select **text**.
+ Enter the configuration json in **section 1** to **Value**.

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/003-config-cwagent.png)

+ Click on **Create parameter**

![Config CWAgent](/images/3-install-config-cwagent/3.2-config-cwagent/004-config-cwagent.png)

#### 3. Apply configuration

{{% notice note %}}
-s option mean restart Cloudwatch Agent after configuring the agent configuration
{{% /notice %}}

+ Configuration file on the local

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c file:/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent.json
```

+ Configuration file in the Systems Manager Parameter Store:

```
sudo amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c ssm:AmazonCloudWatch-Agent-EC2-Configuration
```

With the installation and configuration of the CloudWatch Agent completed, we will configuring high-resolution metrics in the next step.