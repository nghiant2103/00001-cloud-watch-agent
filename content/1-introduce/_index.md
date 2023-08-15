---
title : "Introduction"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : "<b>1. </b>"
---
### CloudWatch Agent

**CloudWatch Agent** is a software package that autonomously and continuously runs on your servers. Using CloudWatch Agent, we can collect metrics and logs from Amazon Elastic Compute Cloud (Amazon EC2), hybrid, and on-premises servers running both Linux and Windows. CloudWatch Agent provides access to more system level and in-guest metrics, in addition to host metrics already provided by Amazon EC2. The agent also lets us collect, aggregate, and summarize metrics and logs from containerized applications and microservices.

CloudWatch Agent supports a modular plugin model that developers can leverage to extend the core agent framework.

Metrics and logs are sent to Amazon CloudWatch for storage and monitoring. The CloudWatch Agent enables additional insight into workloads by capturing OS- and application-specific metrics and logs. In CloudWatch, we can create custom dashboards, create alarms that performs actions, and troubleshoot issues using Amazon CloudWatch Logs.

### High-resolution metrics

Each metric is one of the following:

**Standard resolution**, with data having a one-minute granularity

**High resolution**, with data at a granularity of one second

Metrics produced by AWS services are standard resolution by default. When you publish a custom metric, you can define it as either standard resolution or high resolution. When you publish a high-resolution metric, CloudWatch stores it with a resolution of 1 second, and you can read and retrieve it with a period of 1 second, 5 seconds, 10 seconds, 30 seconds, or any multiple of 60 seconds.

High-resolution metrics can give you more immediate insight into your application's sub-minute activity. Keep in mind that every PutMetricData call for a custom metric is charged, so calling PutMetricData more often on a high-resolution metric can lead to higher charges. For more information about CloudWatch pricing, see Amazon CloudWatch Pricing.

If you set an alarm on a high-resolution metric, you can specify a high-resolution alarm with a period of 10 seconds or 30 seconds, or you can set a regular alarm with a period of any multiple of 60 seconds. There is a higher charge for high-resolution alarms with a period of 10 or 30 seconds.