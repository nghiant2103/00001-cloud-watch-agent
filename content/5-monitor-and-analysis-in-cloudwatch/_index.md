---
title : "Monitor and analysis in CloudWatch"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : "<b>5. </b>"
---

1. Navigate to **AWS CloudWatch**, then choose **All metrics**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/001-monitor-and-analysis-in-cloudwatch.png)

2. On **Custom namespaces** section, click on **WorkshopCWAgent**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/002-monitor-and-analysis-in-cloudwatch.png)

3. Click on **InstanceId**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/003-monitor-and-analysis-in-cloudwatch.png)

4. Select RAM metrics.

  + Select **Metric name** has value **mem_used_percent**.
  + Then click on **Graphed metrics**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/004-monitor-and-analysis-in-cloudwatch.png)

5. Choose **Period** value of **10 seconds**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/005-monitor-and-analysis-in-cloudwatch.png)

6. Choose a time interval of 3 minutes.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/006-monitor-and-analysis-in-cloudwatch.png)

7. The metric every 10 second.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/007-monitor-and-analysis-in-cloudwatch.png)

8. Config dashboard auto refresh every 10 seconds.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/008-monitor-and-analysis-in-cloudwatch.png)

9. Add to dashboard.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/009-monitor-and-analysis-in-cloudwatch.png)

10. Create new dashboard.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/010-monitor-and-analysis-in-cloudwatch.png)

11. Insert name, and click on **Create**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/011-monitor-and-analysis-in-cloudwatch.png)

12. Click on **Add to dashboard**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/012-monitor-and-analysis-in-cloudwatch.png)

13. Navigate to **cw-agent-dashboard**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/013-monitor-and-analysis-in-cloudwatch.png)

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/014-monitor-and-analysis-in-cloudwatch.png)

{{% notice note %}}
You can choose to keep all these resources for the upcoming lab or proceed with the cleanup in the following step.
{{% /notice %}}