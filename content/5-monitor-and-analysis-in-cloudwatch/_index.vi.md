---
title : "Giám sát và phân tích trong CloudWatch"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

1. Truy cập vào **AWS CloudWatch**, rồi chọn **All metrics**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/001-monitor-and-analysis-in-cloudwatch.png)

2. Trong phần **Custom namespaces**, click **WorkshopCWAgent**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/002-monitor-and-analysis-in-cloudwatch.png)

3. Click **InstanceId**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/003-monitor-and-analysis-in-cloudwatch.png)

4. Chọn RAM metrics.

  + Chọn **Metric name** có giá trị **mem_used_percent**.
  + Rồi click **Graphed metrics**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/004-monitor-and-analysis-in-cloudwatch.png)

5. Chọn **Period** giá trị là **10 seconds**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/005-monitor-and-analysis-in-cloudwatch.png)

6. Chọn khoảng thời gian là 3 phút.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/006-monitor-and-analysis-in-cloudwatch.png)

7. Số liệu mỗi 10 giây.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/007-monitor-and-analysis-in-cloudwatch.png)

8. Cấu hình bảng điều khiển tự động làm mới mỗi 10 giây.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/008-monitor-and-analysis-in-cloudwatch.png)

9. Thêm vào dashboard.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/009-monitor-and-analysis-in-cloudwatch.png)

10. Tạo dashboard mới.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/010-monitor-and-analysis-in-cloudwatch.png)

11. Nhập tên, và click **Create**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/011-monitor-and-analysis-in-cloudwatch.png)

12. Click **Add to dashboard**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/012-monitor-and-analysis-in-cloudwatch.png)

13. Truy cập vào **cw-agent-dashboard**.

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/013-monitor-and-analysis-in-cloudwatch.png)

![Monitor and analysis in cloudwatch](/images/5-monitor-and-analysis-in-cloudwatch/014-monitor-and-analysis-in-cloudwatch.png)

{{% notice note %}}
Bạn có thể chọn giữ lại tất cả các tài nguyên này cho bài lab sắp tới hoặc tiến hành dọn dẹp trong bước sau.
{{% /notice %}}