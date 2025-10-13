---
title: "Worklog Tuần 4"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4: Tối ưu hóa hệ thống (Optimizing the System)

Nắm vững 5 trụ cột của AWS Well-Architected Framework:

- **Operational Excellence**: Tự động hóa, giám sát và xử lý sự cố
- **Security**: Kiến trúc zero-trust, tuân thủ và bảo vệ khỏi mối đe dọa
- **Reliability**: Tính khả dụng cao, khôi phục thảm họa và khả năng chịu lỗi
- **Performance**: Tự động mở rộng, caching và tối ưu hóa tài nguyên
- **Cost Optimization**: Right-sizing, reserved capacity và phân tích chi phí

### Các công việc cần triển khai trong tuần này

<!-- markdownlint-disable MD033 -->

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                    |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 2   | **Operational Excellence**:<br>- Tự động tắt server và gửi thông báo Slack với AWS Lambda<br>+ Tạo hệ thống giám sát với Amazon CloudWatch và Grafana<br>+ Quản lý tài nguyên theo nhóm với Tag và Resource Groups<br>- Quản lý truy cập EC2 với Tag thông qua IAM<br>+ Tự động hóa quản lý dịch vụ với AWS Systems Manager<br>- Khởi tạo Infrastructure as Code với AWS CloudFormation       | 29/09/2025   | 29/09/2025      | <https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i>                                             |
| 3   | **Security**:<br>- Thiết lập Single Sign-On (Amazon SSO) cho tổ chức<br>+ Giới hạn quyền người dùng với IAM Permission Boundary<br>+ Giới hạn Role Transfer bằng Condition<br>- Kiểm tra security benchmarks với AWS Security Hub<br>+ Bảo vệ ứng dụng và API với Web Application Firewall (AWS WAF)<br>- Quản lý khóa với Key Management Service (AWS KMS)                                   | 30/09/2025   | 30/09/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | **Reliability**:<br>- Triển khai kế hoạch sao lưu hệ thống với AWS Backup<br>+ Kết nối Virtual Private Clouds (VPCs) với VPC Peering<br>- Quản lý kết nối tập trung với AWS Transit Gateway                                                                                                                                                                                                   | 01/10/2025   | 01/10/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | **Performance**:<br>- Triển khai ứng dụng với Docker<br>+ Triển khai ứng dụng lên Amazon Elastic Container Service (Amazon ECS)<br>+ Triển khai ứng dụng với AWS CodePipeline<br>- Lưu trữ dữ liệu không giới hạn trên AWS với File Storage Gateway<br>+ Triển khai Universal Repository cho Windows sử dụng FSx<br>- Xây dựng Data Lake trên AWS<br>+ Kiến trúc nâng cao với Amazon DynamoDB | 02/10/2025   | 02/10/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | **Cost Optimization**:<br>- Tối ưu chi phí với Savings Plans, Reserved Instance, Reserved DB Instance<br>+ Chọn right-sizing phù hợp cho Amazon EC2 Resource Optimization<br>+ Trực quan hóa chi phí sử dụng trên AWS<br>- Phân tích chi phí sử dụng nâng cao với AWS Glue và Amazon Athena<br>- Ôn tập tổng hợp 5 trụ cột Well-Architected Framework                                         | 03/10/2025   | 03/10/2025      | <https://cloudjourney.awsstudygroup.com><br><https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | **Reliability**:<br>- Triển khai kế hoạch sao lưu hệ thống với AWS Backup<br>+ Kết nối Virtual Private Clouds (VPCs) với VPC Peering<br>- Quản lý kết nối tập trung với AWS Transit Gateway                                                                                                                                                                                                   | 01/10/2025   | 01/10/2025      | <https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i>                                             |
| 5   | **Performance**:<br>- Triển khai ứng dụng với Docker<br>+ Triển khai ứng dụng lên Amazon Elastic Container Service (Amazon ECS)<br>+ Triển khai ứng dụng với AWS CodePipeline<br>- Lưu trữ dữ liệu không giới hạn trên AWS với File Storage Gateway<br>+ Triển khai Universal Repository cho Windows sử dụng FSx<br>- Xây dựng Data Lake trên AWS<br>+ Kiến trúc nâng cao với Amazon DynamoDB | 02/10/2025   | 02/10/2025      | <https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i>                                             |
| 6   | **Cost Optimization**:<br>- Tối ưu chi phí với Savings Plans, Reserved Instance, Reserved DB Instance<br>+ Chọn right-sizing phù hợp cho Amazon EC2 Resource Optimization<br>+ Trực quan hóa chi phí sử dụng trên AWS<br>- Phân tích chi phí sử dụng nâng cao với AWS Glue và Amazon Athena<br>- Ôn tập tổng hợp 5 trụ cột Well-Architected Framework                                         | 03/10/2025   | 03/10/2025      | <https://www.youtube.com/watch?v=AQlsd0nWdZk&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i>                                             |

<!-- markdownlint-enable MD033 -->

### Kết quả đạt được tuần 4

#### Đã làm được gì

- **Operational Excellence**: Tự động hóa tắt server, giám sát hệ thống với CloudWatch/Grafana, quản lý tài nguyên với Tags
- **Security**: Thiết lập SSO, IAM Permission Boundary, AWS WAF, KMS key management, Security Hub benchmarks
- **Reliability**: Triển khai AWS Backup, VPC Peering, Transit Gateway cho hệ thống đáng tin cậy
- **Performance**: Docker/ECS deployment, CodePipeline automation, File Storage Gateway, FSx, Data Lake, DynamoDB architecture
- **Cost Optimization**: Savings Plans, Reserved Instances, right-sizing, cost visualization, advanced analytics với Glue/Athena
- Thực hành tối ưu hóa toàn diện: từ vận hành, bảo mật đến hiệu suất và chi phí
