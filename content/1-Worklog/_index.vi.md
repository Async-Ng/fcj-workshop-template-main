---
title: "Nhật ký công việc"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

**Trong trang này** tôi sẽ giới thiệu quá trình học tập AWS của mình trong **12 tuần** của chương trình thực tập. Mỗi tuần tôi đã tập trung vào những chủ đề khác nhau, từ các dịch vụ cơ bản đến các giải pháp nâng cao.

Chương trình được thiết kế theo hướng tiến bộ, giúp tôi xây dựng nền tảng kiến thức vững chắc và kỹ năng thực hành cần thiết cho vai trò Cloud Engineer/Solution Architect.

## Chương trình học tập 12 tuần

**Tuần 1:** [AWS Fundamentals - Nền tảng cơ bản](1.1-week1/)

- Tạo và bảo mật tài khoản AWS, quản lý chi phí với Budgets
- Nắm vững IAM (Identity and Access Management) và phân quyền
- Hiểu kiến trúc VPC và triển khai EC2 đầu tiên

**Tuần 2:** [Advanced Networking - Mạng nâng cao](1.2-week2/)

- Thiết lập Hybrid DNS với Route 53 Resolver
- Cấu hình VPC Peering và AWS Transit Gateway
- Lên kế hoạch cho dự án cuối kỳ

**Tuần 3:** [Comprehensive AWS Services - Dịch vụ toàn diện](1.3-week3/)

- Tìm hiểu sâu EC2: Windows/Linux, Custom AMI, EBS management
- Làm quen IAM Role, AWS Cloud9, và Amazon S3 static hosting
- Quản lý database với RDS và Lightsail, Autoscaling với CloudWatch

**Tuần 4:** [System Optimization - Tối ưu hóa hệ thống](1.4-week4/)

- **Operational Excellence**: Tự động hóa, giám sát và Infrastructure as Code
- **Security**: SSO, IAM boundaries, WAF, và Key Management
- **Reliability**: AWS Backup, VPC Peering, Transit Gateway
- **Performance**: Docker/ECS, CodePipeline, Data Lake, DynamoDB
- **Cost Optimization**: Savings Plans, right-sizing, cost analysis

**Tuần 5:** [Phát triển dự án & Cài đặt môi trường Local](1.5-week5/)

- Dịch các blogs được giao cho FCJ
- Ôn tập và củng cố kiến thức tuần 4
- Thiết lập môi trường phát triển cho dự án sắp tới
- Cấu hình các dịch vụ AWS local (DynamoDB local với Docker)
- Làm quen với AWS CDK và tổ chức cấu trúc dự án

**Tuần 6:** [Hiện đại hóa Ứng dụng & Microservices](1.6-week6/)

- Di chuyển ứng dụng nguyên khối sang kiến trúc cloud-native
- Triển khai xác thực và bảo mật với Amazon Cognito
- Xây dựng microservices với API Gateway và Lambda
- Cấu hình điều phối và quy trình CI/CD
- Phát triển Single Page Applications và tích hợp dịch vụ AI

**Tuần 7:** [Containers & Kubernetes](1.7-week7/)

- Triển khai ứng dụng sử dụng Amazon Lightsail Containers
- Thiết lập và quản lý Amazon EKS clusters
- Triển khai CI/CD pipelines với AWS CodePipeline
- Chuyển đổi ứng dụng nguyên khối sang microservices với Docker và AWS Fargate
- Tích hợp GitHub với EKS cho automated deployments

**Tuần 8:** [Ôn tập Tổng hợp & Thi Giữa Kỳ](1.8-week8/)

- Ôn tập Nền tảng AWS (Tuần 1-2): EC2, S3, VPC, networking
- Ôn tập Bảo mật & Định danh (Tuần 3-4): IAM, Cognito, best practices
- Ôn tập Serverless & Modernization (Tuần 5-6): Lambda, API Gateway, DynamoDB
- Ôn tập Containers & CI/CD (Tuần 7): Docker, EKS, CodePipeline, Fargate
- Thi Giữa Kỳ bao gồm tất cả nội dung từ Tuần 1-7

**Tuần 9:** [Data Lake & Analytics với AI/ML](1.9-week9/)

- Xây dựng Data Lake toàn diện sử dụng dịch vụ serverless của AWS
- Nắm vững kỹ năng thu thập, lưu trữ, chuyển đổi và phân tích dữ liệu
- Học tập các Dịch vụ Analytics trên AWS: Glue, Athena, Kinesis, và Redshift
- Tạo dashboards tương tác với Amazon QuickSight
- Bắt đầu với machine learning sử dụng Amazon SageMaker
- Khám phá Generative AI với Amazon Bedrock
- Feature Engineering và huấn luyện/triển khai mô hình XGBoost

**Tuần 10:** [Ôn tập Hệ thống Backend & Tích hợp AI](1.10-week10/)

- Test lại toàn bộ hệ thống Backend được tạo bằng AI
- Hiểu rõ logic của xác thực, phân quyền và quản lý phòng trọ
- Kiểm tra các endpoints và chức năng API
- Ôn tập code và logic của tính năng đề xuất AI
- Nắm vững tích hợp AWS Bedrock với filter logic
- Hiểu toàn diện về tất cả các tính năng liên quan đến AI

**Tuần 11:** [Workshop DevOps & Ôn tập Proposal](1.11-week11/)

- Tham dự workshop tăng cường về DevOps và CI/CD
- Hiểu DevOps Mindset và cách áp dụng trong thực tế
- Nắm vững AWS DevOps Services và CI/CD Pipeline
- Tìm hiểu Infrastructure as Code (IaC) và best practices
- Viết lại tài liệu proposal dự án
- Kiểm tra và audit toàn diện source code

**Tuần 12:** [Bảo trì Dự án & Điều chỉnh](1.12-week12/)

- Test các prompt mới cho endpoint tìm kiếm của dự án
- Sửa các lỗi endpoint được báo cáo
- Phối hợp với team frontend để điều chỉnh giao diện
- Tiếp tục chỉnh sửa và cải thiện các endpoint cần thiết

**Tuần 13:** [Fix tính năng AI Search & Tích hợp](1.13-Week13/)

- Thử nghiệm các biến thể prompt và cải thiện chất lượng tìm kiếm ngữ nghĩa
