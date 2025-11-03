---
title: "Worklog Tuần 7"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 7:

- Học cách triển khai container hóa với Amazon Lightsail Containers và Docker.
- Bắt đầu với điều phối Kubernetes sử dụng Amazon EKS.
- Triển khai CI/CD pipeline với AWS CodePipeline.
- Chuyển đổi ứng dụng nguyên khối thành microservices sử dụng Docker và AWS Fargate.
- Tích hợp quy trình CI/CD với EKS, CodePipeline và GitHub.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------------------------------------------- |
| 2   | - **Getting Started with Amazon Lightsail Containers** <br>&emsp; + Tìm hiểu cơ bản dịch vụ Lightsail container <br>&emsp; + Triển khai ứng dụng container hóa <br>&emsp; + Cấu hình thiết lập container                                                                                                                                                                                                                                 | 20/10/2025   | 20/10/2025      | <https://aws.amazon.com/lightsail/>                                           |
| 3   | - **Get started with Amazon EKS** <br>&emsp; + Thiết lập EKS cluster <br>&emsp; + Cấu hình kubectl <br>&emsp; + Triển khai ứng dụng lên EKS <br>&emsp; + Quản lý pods và services                                                                                                                                                                                                                                                        | 21/10/2025   | 21/10/2025      | <https://aws.amazon.com/eks/>                                                 |
| 4   | - **CI/CD with CodePipeline** <br>&emsp; + Tạo CodePipeline <br>&emsp; + Cấu hình source và build stages <br>&emsp; + Thiết lập tự động hóa deployment <br>&emsp; + Kiểm tra thực thi pipeline                                                                                                                                                                                                                                           | 22/10/2025   | 22/10/2025      | <https://aws.amazon.com/codepipeline/>                                        |
| 5   | - **Monolith to Microservices with Docker and AWS Fargate** <br>&emsp; + Phân tách ứng dụng nguyên khối <br>&emsp; + Container hóa microservices <br>&emsp; + Triển khai lên Fargate <br>&emsp; + Cấu hình giao tiếp giữa các services <br> - **CI/CD on EKS with CodePipeline and GitHub** <br>&emsp; + Tích hợp GitHub repository <br>&emsp; + Cấu hình pipeline cho EKS deployment <br>&emsp; + Tự động hóa quy trình build và deploy | 23/10/2025   | 23/10/2025      | <https://aws.amazon.com/fargate/> <br> <https://aws.amazon.com/codepipeline/> |
| 6   | - **Ôn tập và Củng cố Kiến thức** <br>&emsp; + Ôn lại các khái niệm container và Kubernetes <br>&emsp; + Thực hành khắc phục sự cố CI/CD pipeline <br>&emsp; + Củng cố các mẫu kiến trúc microservices <br>&emsp; + Chuẩn bị cho tuần ôn tập tổng hợp tiếp theo                                                                                                                                                                          | 24/10/2025   | 24/10/2025      |                                                                               |

### Kết quả đạt được tuần 7:

- Triển khai thành công ứng dụng container hóa sử dụng Amazon Lightsail Containers:

  - Hiểu kiến trúc dịch vụ Lightsail container
  - Triển khai và quản lý Docker containers
  - Cấu hình scaling và networking cho container

- Thiết lập và cấu hình Amazon EKS cluster:

  - Tạo EKS cluster với node groups phù hợp
  - Cấu hình kubectl cho quản lý cluster
  - Triển khai và quản lý ứng dụng container hóa trên Kubernetes
  - Làm việc với pods, deployments và services

- Triển khai CI/CD pipeline với AWS CodePipeline:

  - Tạo quy trình build và deployment tự động
  - Tích hợp source control với các pipeline stages
  - Cấu hình tự động hóa deployment cho ứng dụng container hóa

- Chuyển đổi ứng dụng nguyên khối thành kiến trúc microservices:

  - Phân tách ứng dụng nguyên khối thành các services độc lập
  - Container hóa microservices sử dụng Docker
  - Triển khai microservices lên AWS Fargate
  - Cấu hình service discovery và giao tiếp

- Tích hợp CI/CD với EKS và GitHub:

  - Kết nối GitHub repositories với CodePipeline
  - Tự động hóa build, test và deployment lên EKS
  - Triển khai GitOps workflows cho Kubernetes deployments

- Có kinh nghiệm thực hành với:
  - Điều phối và quản lý container
  - Các khái niệm và thao tác Kubernetes
  - Best practices cho CI/CD với ứng dụng container hóa
  - Serverless container deployment với Fargate
