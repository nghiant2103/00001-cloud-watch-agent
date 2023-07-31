---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### CloudWatch Agent

CloudWatch Agent là một gói phần mềm hoạt động tự động và liên tục trên máy chủ của bạn. Sử dụng CloudWatch Agent, chúng ta có thể thu thập các metrics và logs từ máy chủ Amazon Elastic Compute Cloud (Amazon EC2), hybrid và on-premises chạy cả trên hệ điều hành Linux và Windows. CloudWatch Agent cung cấp truy cập vào các số liệu và chỉ số cấp hệ thống nhiều hơn và số liệu từ bên trong khách hàng, bổ sung cho các chỉ số máy chủ đã được cung cấp bởi Amazon EC2. Agent cũng cho phép chúng ta thu thập, tổng hợp và tóm tắt metrics và logs từ các ứng dụng và dịch vụ micro được đóng gói trong container.

CloudWatch Agent hỗ trợ mô hình plugin có tính modular mà các nhà phát triển có thể tận dụng để mở rộng khung gốc của agent.

Các metrics và logs được gửi đến Amazon CloudWatch để lưu trữ và giám sát. CloudWatch Agent cho phép có cái nhìn sâu hơn về các khối công việc bằng cách thu thập metrics và logs cụ thể cho hệ điều hành và ứng dụng. Trong CloudWatch, chúng ta có thể tạo bảng điều khiển tùy chỉnh, tạo cảnh báo thực hiện các hành động và khắc phục sự cố bằng cách sử dụng Amazon CloudWatch Logs.

### Metrics với độ phân giải cao

Mỗi số liệu độ đo là một trong các loại sau:

**Độ phân giải tiêu chuẩn**, với dữ liệu có độ chi tiết trên phút

**Độ phân giải cao**, với dữ liệu có độ chi tiết trên giây

Các metrics được tạo bởi các dịch vụ AWS mặc định là độ phân giải tiêu chuẩn. Khi bạn xuất bản một metrics tùy chỉnh, bạn có thể xác định nó là độ phân giải tiêu chuẩn hoặc độ phân giải cao. Khi bạn xuất bản một metrics độ phân giải cao, CloudWatch lưu trữ nó với độ phân giải 1 giây và bạn có thể đọc và truy xuất nó với chu kỳ 1 giây, 5 giây, 10 giây, 30 giây hoặc bất kỳ bội số nào của 60 giây.

Metrics độ phân giải cao có thể cung cấp cái nhìn tức thì hơn về hoạt động trong vòng dưới một phút của ứng dụng của bạn. Hãy lưu ý rằng mỗi lệnh PutMetricData cho một metrics tùy chỉnh sẽ bị tính phí, do đó gọi PutMetricData thường xuyên hơn cho một metrics độ phân giải cao có thể dẫn đến việc tính phí cao hơn. Để biết thêm thông tin về giá CloudWatch, xem Bảng giá Amazon CloudWatch.

Nếu bạn thiết lập một cảnh báo trên một metrics độ phân giải cao, bạn có thể chỉ định một cảnh báo độ phân giải cao với chu kỳ 10 giây hoặc 30 giây, hoặc bạn có thể thiết lập một cảnh báo thông thường với chu kỳ bất kỳ bội số nào của 60 giây. Có một mức phí cao hơn cho các cảnh báo độ phân giải cao với chu kỳ 10 hoặc 30 giây.