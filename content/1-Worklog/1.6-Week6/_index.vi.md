---
title: "Worklog Tuần 6"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

- Phân tách Monolith thành các microservice và xác định bounded contexts.
- Triển khai microservice serverless và cấu hình điều phối (CodeStar).
- Xây dựng microservice Scan & Query và Calculator; thiết kế và bảo vệ API.
- Tự động hóa triển khai microservices (CI/CD) và bật quy trình auto-release.
- Tạo và bảo mật Single Page Application với AAA và theo dõi hiệu năng bằng X-Ray.
- Khám phá dịch vụ AI: Polly, Rekognition và Lex.

{{% notice warning %}}
Dịch vụ AWS CodeStar đã ngưng. Chỉ đọc để tham khảo
{{%/notice%}}
### Các công việc cần triển khai trong tuần này:


> | Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                  |
> | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | ------------------------------------------------------------------------------- |
> | 2   | - **Di chuyển ứng dụng Monolith:** <br>&emsp; + Kiểm thử cục bộ bằng Eclipse IDE <br>&emsp; + Triển khai lên ElasticBeanstalk <br>&emsp; + Cập nhật ứng dụng <br>&emsp; + Truy vấn API bằng Eclipse IDE <br> - **Tự động phát hành ứng dụng:** <br>&emsp; + Cấu hình phát hành tự động <br>&emsp; + Triển khai ứng dụng <br>&emsp; + Triển khai Windows Service sử dụng AWS CodeDeploy <br>&emsp; + Giám sát dịch vụ                                                                                                                                                                                                                                               | 13/10/2025   | 13/10/2025      | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |
> | 3   | - **Code tính năng xác thực với Cognito:** <br>&emsp; + Cấu hình Cognito User Pool <br>&emsp; + Triển khai luồng đăng ký <br>&emsp; + Triển khai luồng đăng nhập <br>&emsp; + Cấu hình app clients                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 14/10/2025   | 14/10/2025      | <https://docs.aws.amazon.com/cognito/>                                          |
> | 4   | - **Triển khai đăng nhập bằng số điện thoại với OTP sử dụng SNS:** <br>&emsp; + Cấu hình SNS để gửi SMS <br>&emsp; + Tích hợp tạo OTP <br>&emsp; + Triển khai xác thực OTP <br>&emsp; + Kiểm thử xác thực số điện thoại <br> - **Điều chỉnh lại cấu trúc bảng UserProfile trong DynamoDB:** <br>&emsp; + Thiết kế schema mới <br>&emsp; + Cập nhật access patterns <br>&emsp; + Thêm các thuộc tính mới                                                                                                                                                                                                                                                            | 15/10/2025   | 15/10/2025      | <https://docs.aws.amazon.com/sns/> <br> <https://docs.aws.amazon.com/dynamodb/> |
> | 5   | - **Tạo Microservice:** <br>&emsp; + Tạo một microservice <br>&emsp; + Mở rộng microservices serverless <br>&emsp; + Cấu hình điều phối với CodeStar (tham khảo — dịch vụ đã ngưng) <br>&emsp; + Thử thách - Public API của microservice <br> - **Tái cấu trúc dữ liệu và workflow:** <br>&emsp; + Tạo Microservice Scan & Query <br>&emsp; + Tự động hóa Microservice của bạn <br>&emsp; + Tạo API cho Microservice <br>&emsp; + Thử thách - Nâng cấp TripSearch Microservice <br>&emsp; + Tạo Calculator Microservice sử dụng AWS Step Functions <br>&emsp; + Thử thách - Nâng cấp Calculator Service <br>&emsp; + Thử thách - Triển khai workflow Image Manager | 16/10/2025   | 16/10/2025      | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |
> | 6   | - **Tạo và xác thực Single Page Application:** <br>&emsp; + Tạo Single Page Application <br>&emsp; + Cấu hình Authentication, Authorization và Accounting (AAA) <br>&emsp; + Theo dõi hiệu năng ứng dụng bằng AWS X-Ray <br>&emsp; + Thử thách <br> - **Trải nghiệm dịch vụ AI trên AWS:** <br>&emsp; + Thêm giọng nói bằng Amazon Polly <br>&emsp; + Thêm nhận diện đối tượng bằng Amazon Rekognition <br>&emsp; + Thêm Chat Bot bằng Amazon Lex <br>&emsp; + Các bài tập thử thách                                                                                                                                                                               | 17/10/2025   | 17/10/2025      | <https://cloudjourney.awsstudygroup.com/4-modernize/>                           |

### Kết quả đạt được tuần 6:

Tuần này, chúng tôi đã tiến hành hiện đại hóa ứng dụng và triển khai một số tính năng không cần máy chủ. Các thành tựu chính phù hợp với mục tiêu:

- Tự động hóa di chuyển và phát hành Monolith

  - Xác thực Monolith cục bộ (Eclipse) và triển khai ứng viên di chuyển lên Elastic Beanstalk.

  - Cấu hình luồng tự động phát hành ban đầu và chuẩn bị triển khai Dịch vụ Windows thông qua AWS CodeDeploy.

- Xác thực và bảo mật

  - Triển khai xác thực người dùng dựa trên Cognito (đăng ký/đăng nhập) và xác thực JWT.
  - Thêm luồng OTP qua điện thoại sử dụng SNS với giới hạn tốc độ và xác minh.

- Dữ liệu và dịch vụ vi mô

  - Tái cấu trúc lược đồ DynamoDB UserProfile để hỗ trợ các mẫu truy cập và di chuyển mới.
  - Tạo bản thiết kế cho các dịch vụ vi mô Quét & Truy vấn và Máy tính; thiết kế API và quy trình làm việc Step Functions cho máy tính.

- Phối hợp vi mô và CI/CD

  - Xây dựng bộ khung vi mô không cần máy chủ và lên kế hoạch phối hợp với CodeStar.

  - Cấu hình các bước triển khai tự động cho các dịch vụ vi mô và quy trình triển khai đã được xác thực.

- SPA và khả năng quan sát

  - Scaffolder cho Ứng dụng Trang Đơn đã được chuẩn bị; cấu hình các cân nhắc về xác thực và AAA, đồng thời tích hợp theo dõi X-Ray để kiểm tra hiệu suất.

- Thử nghiệm AI
  - Các ví dụ và bản demo tích hợp cho Amazon Polly, Rekognition và Lex để khám phá việc bổ sung các tính năng nhận dạng giọng nói, nhận dạng đối tượng và bot trò chuyện.
