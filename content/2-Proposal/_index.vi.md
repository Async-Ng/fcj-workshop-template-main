---
title: "Bản đề xuất"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Smart Boarding House Finder

## Nền Tảng Gợi Ý Trọ Thông Minh AWS Serverless

### 1. Tóm tắt điều hành

Dự án "Smart Boarding House Finder" hướng đến việc xây dựng một nền tảng tìm trọ thông minh cho sinh viên và người đi làm tại Việt Nam, sử dụng kiến trúc AWS Serverless và dịch vụ AI Recommendation. Hệ thống cho phép cá nhân hóa kết quả tìm kiếm dựa trên thu nhập, thói quen sinh hoạt, và tiện ích xung quanh, đồng thời giúp chủ trọ dễ dàng tiếp cận đúng nhóm khách hàng mục tiêu. Ứng dụng web (Frontend: React, Backend: AWS Lambda) lưu trữ dữ liệu bằng S3, quản lý người dùng qua Cognito, và gợi ý thông minh thông qua TensorFlow.js hoặc logic rule-based. Dashboard thống kê sử dụng AWS QuickSight.

### 2. Tuyên bố vấn đề

#### Vấn đề hiện tại

Các nền tảng hiện nay chỉ hỗ trợ tìm kiếm cơ bản theo giá, vị trí, diện tích. Người dùng vẫn phải lọc thủ công hàng trăm tin đăng mà không có gợi ý cá nhân hóa dựa trên thu nhập, thói quen sinh hoạt hay tiện ích xung quanh.

#### Giải pháp

Nền tảng tìm trọ thông minh trên AWS, gợi ý phòng trọ theo thu nhập và lối sống, hiển thị tiện ích xung quanh qua tích hợp OpenStreetMap, tự động gửi thông báo khi có phòng phù hợp, và xây dựng API serverless bằng AWS Lambda để đảm bảo khả năng mở rộng và tiết kiệm chi phí.

#### Lợi ích và hoàn vốn đầu tư

Nền tảng cung cấp trải nghiệm tìm kiếm cá nhân hóa cho sinh viên và người đi làm, giúp chủ trọ tiếp cận đúng khách hàng mục tiêu, giảm thời gian lọc thủ công, và cung cấp thông báo thời gian thực cho tin đăng mới. Hoạt động hoàn toàn trong AWS Free Tier ở giai đoạn MVP (~$0.5/tháng), nền tảng có thể mở rộng lên AI Recommendation đầy đủ khi đủ dữ liệu, duy trì trải nghiệm gợi ý thông minh mà không phát sinh chi phí lớn ở giai đoạn đầu.

### 3. Kiến trúc giải pháp

Hệ thống sử dụng kiến trúc AWS Serverless và dịch vụ open-source miễn phí để tạo nền tảng tiết kiệm chi phí và có khả năng mở rộng.

| Thành phần            | Dịch vụ / Công nghệ        |
| --------------------- | -------------------------- |
| Frontend Hosting      | AWS Amplify / CloudFront   |
| API Backend           | AWS Lambda + API Gateway   |
| Database              | DynamoDB                   |
| File Storage          | S3                         |
| User Management       | Cognito                    |
| Notifications         | AWS SES                    |
| Map & Location        | OpenStreetMap + Leaflet.js |
| Recommendation Engine | Rule-based + TensorFlow.js |
| Analytics & Dashboard | AWS QuickSight             |

![Kiến Trúc Smart Boarding House Finder](/images/2-Proposal/AWSProject.drawio.png)

### Dịch vụ AWS sử dụng

- **AWS Lambda**: Xử lý các yêu cầu API và thực thi logic gợi ý.
- **Amazon API Gateway**: Cung cấp các endpoint RESTful API cho giao tiếp frontend.
- **Amazon DynamoDB**: Lưu trữ hồ sơ người dùng, danh sách phòng trọ và sở thích.
- **Amazon S3**: Lưu trữ hình ảnh và tài nguyên tĩnh.
- **AWS Amplify / CloudFront**: Lưu trữ và phân phối ứng dụng React frontend.
- **Amazon Cognito**: Quản lý xác thực và phân quyền người dùng.
- **AWS SES**: Gửi thông báo email cho danh sách phòng trọ phù hợp.
- **AWS QuickSight**: Cung cấp bảng điều khiển phân tích thống kê sử dụng.

### Thiết kế thành phần

- **Ứng dụng Frontend**: SPA dựa trên React được lưu trữ trên AWS Amplify/CloudFront cho giao diện người dùng responsive.
- **Lớp API**: Các hàm AWS Lambda đằng sau API Gateway xử lý logic nghiệp vụ và thao tác dữ liệu.
- **Cơ sở dữ liệu**: DynamoDB lưu trữ dữ liệu có cấu trúc với schema linh hoạt cho thông tin người dùng và danh sách.
- **Lưu trữ**: S3 buckets lưu trữ hình ảnh phòng trọ và các tệp tĩnh khác với CloudFront CDN.
- **Công cụ gợi ý**: Logic rule-based trong Lambda (MVP), với khả năng tích hợp TensorFlow.js cho ML phía client.
- **Tích hợp bản đồ**: OpenStreetMap với Leaflet.js hiển thị vị trí và tiện ích xung quanh.
- **Hệ thống thông báo**: AWS SES kích hoạt cảnh báo email khi có danh sách phù hợp mới.
- **Quản lý người dùng**: Amazon Cognito xử lý đăng ký, đăng nhập và quản lý phiên.

### 4. Triển khai kỹ thuật

#### Phương pháp Recommendation Engine

- **Giai đoạn MVP**: Logic rule-based xử lý trong AWS Lambda (Node.js) dựa trên sở thích người dùng, phạm vi thu nhập và bộ lọc vị trí.
- **Giai đoạn mở rộng**: Tích hợp TensorFlow.js để xử lý dữ liệu phía client và nâng cao độ chính xác gợi ý.
- **Giai đoạn nâng cao**: Huấn luyện mô hình ML bằng Amazon Personalize khi đủ dữ liệu người dùng.

#### Yêu cầu kỹ thuật

- **Frontend**: React.js với thiết kế responsive, Leaflet.js cho tích hợp bản đồ, AWS Amplify SDK cho giao tiếp backend.
- **Backend**: Hàm Lambda Node.js, AWS SDK cho thao tác DynamoDB và S3, API Gateway cho các endpoint RESTful.
- **Cơ sở dữ liệu**: Các bảng DynamoDB cho người dùng, danh sách, sở thích và lịch sử tìm kiếm với các index phù hợp.
- **Lưu trữ**: S3 buckets với lifecycle policies để tối ưu hình ảnh và quản lý chi phí.
- **Xác thực**: Cognito User Pools để quản lý người dùng an toàn với xác minh email.
- **Thông báo**: Templates SES cho cảnh báo email tự động được kích hoạt bởi hàm Lambda.

### 5. Lộ trình & Mốc triển khai

**Lộ trình dự án**

- **Tuần 1-2**: Thiết kế kiến trúc AWS và thiết lập môi trường phát triển.
- **Tuần 3-4**: Phát triển giao diện frontend và triển khai các endpoint API.
- **Tuần 5**: Xây dựng và tích hợp công cụ AI Recommendation (MVP rule-based).
- **Tuần 6**: Kiểm thử, sửa lỗi và chuẩn bị demo.
- **Sau triển khai**: Theo dõi chi phí và hiệu năng, thu thập phản hồi người dùng để cải tiến.

### 6. Ước tính ngân sách

### Chi phí hạ tầng

| Thành phần           | Dịch vụ                    | Chi phí ước tính |
| -------------------- | -------------------------- | ---------------- |
| Lambda + API Gateway | Backend                    | $0.10/tháng      |
| DynamoDB             | Database                   | $0.10/tháng      |
| S3 + CloudFront      | Storage                    | $0.20/tháng      |
| Cognito              | Authentication             | $0.05/tháng      |
| SES + QuickSight     | Notifications + Analytics  | $0.05/tháng      |
| Map & Location       | OpenStreetMap + Leaflet    | $0.00            |
| AI Engine            | Rule-based / TensorFlow.js | $0.00            |

**Tổng chi phí ước tính**: ~$0.50/tháng (trong AWS Free Tier)

**Lưu ý**: Tất cả dịch vụ được thiết kế để hoạt động trong giới hạn AWS Free Tier ở giai đoạn MVP, với chi phí tối thiểu cho lưu trữ và truyền dữ liệu.

### 7. Đánh giá rủi ro

#### Ma trận rủi ro

- **Vượt giới hạn AWS Free Tier**: Ảnh hưởng trung bình, xác suất trung bình.
- **Lỗi cấu hình IAM hoặc API**: Ảnh hưởng cao, xác suất thấp.
- **Thiếu kỹ năng AWS chuyên sâu**: Ảnh hưởng trung bình, xác suất trung bình.

#### Chiến lược giảm thiểu

- **Quản lý chi phí**: Triển khai AWS Budgets với cảnh báo để theo dõi chi tiêu và ngăn vượt mức.
- **Bảo mật**: Cấu hình IAM theo nguyên tắc least privilege với kiểm soát truy cập dựa trên vai trò.
- **Độ phức tạp kỹ thuật**: Bắt đầu với AI rule-based ở giai đoạn MVP để giảm chi phí huấn luyện và độ phức tạp.

#### Kế hoạch dự phòng

- **Vượt ngân sách**: Thu nhỏ quy mô về dịch vụ Free Tier hoặc tạm dừng các tính năng không thiết yếu.
- **Vấn đề kỹ thuật**: Duy trì tài liệu toàn diện và sử dụng AWS CloudFormation để rollback hạ tầng.
- **Vấn đề hiệu năng**: Triển khai chiến lược caching và tối ưu thời gian thực thi hàm Lambda.

### 8. Kết quả kỳ vọng

#### Cải tiến kỹ thuật

- **Ra mắt MVP**: Nền tảng hoạt động đầy đủ chạy hoàn toàn trong AWS Free Tier.
- **Gợi ý thông minh**: Hệ thống rule-based cung cấp đề xuất cá nhân hóa mà không tốn chi phí huấn luyện AI.
- **Khả năng mở rộng**: Kiến trúc sẵn sàng tích hợp AI Recommendation đầy đủ khi đủ dữ liệu.
- **Trải nghiệm người dùng**: Giao diện trực quan với tìm kiếm thời gian thực và thông báo tự động.

#### Giá trị dài hạn

- **Thu thập dữ liệu**: Xây dựng tập dữ liệu hành vi người dùng cho huấn luyện mô hình ML tương lai.
- **Phát triển nền tảng**: Chuyển đổi dần từ gợi ý rule-based sang AI-powered.
- **Hiệu quả chi phí**: Duy trì trải nghiệm gợi ý thông minh mà không phát sinh chi phí đáng kể ở giai đoạn đầu.
- **Xác thực thị trường**: Bằng chứng khái niệm cho tìm kiếm nhà trọ thông minh tại thị trường Việt Nam.
