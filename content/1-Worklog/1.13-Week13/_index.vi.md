---
title: "Worklog Tuần 13"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13

- Hoàn thiện và fix tính năng AI Search (semantic search) trong dự án FindNest.
- Kiểm thử end-to-end từ frontend → API Gateway → Lambda → Bedrock/DynamoDB.
- Cải thiện prompt, xử lý lỗi và tối ưu hiệu năng trả về kết quả tìm kiếm.

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc                                                        | Ngày bắt đầu | Ngày hoàn thành | Ghi chú                                |
| --- | ---------------------------------------------------------------- | ------------ | --------------- | -------------------------------------- |
| 2   | Thử nghiệm các câu prompt khác nhau để cải thiện semantic search | 01/12/2025   | 01/12/2025      | So sánh few-shot vs minimal prompt     |
| 3   | Debug Lambda xử lý tìm kiếm và kiểm tra prompt gửi Bedrock       | 02/12/2025   | 02/12/2025      | Sửa format input cho Bedrock           |
| 4   | Thêm validation cho dữ liệu đầu vào và fallback logic            | 03/12/2025   | 03/12/2025      | Tránh trả về kết quả rác               |
| 5   | Tối ưu truy vấn DynamoDB và caching tạm thời                     | 04/12/2025   | 04/12/2025      | Dùng TTL và in-memory cache cho Lambda |
| 6   | Test tích hợp với FE, thu thập phản hồi và fix UI edgecases      | 05/12/2025   | 05/12/2025      | Đồng bộ format request/response        |

### Kết quả đạt được tuần 13

- Tính năng AI Search trả về kết quả phù hợp hơn với truy vấn người dùng; độ tương thích ngữ nghĩa (semantic relevance) được cải thiện rõ rệt.
- Latency giảm ~30% cho các truy vấn phổ biến nhờ caching tạm thời trong Lambda và tối ưu truy vấn DynamoDB.
- Các lỗi parse input được xử lý; frontend nhận mã lỗi rõ ràng khi gửi dữ liệu sai định dạng.
- Tích hợp end-to-end (FE → API Gateway → Lambda → Bedrock/DynamoDB) hoạt động ổn định trên môi trường dev/staging.
