---
title: "Worklog Tuần 9"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 9:

- Xây dựng Data Lake trên AWS sử dụng các dịch vụ serverless.
- Nắm vững kỹ năng thu thập, lưu trữ, chuyển đổi và phân tích dữ liệu.
- Thiết kế và triển khai kiến trúc Data Lake không máy chủ với xử lý real-time và batch.
- Tạo visualizations và dashboards sử dụng các công cụ phân tích AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Xây dựng Data Lake trên AWS** <br> - Thu thập và lưu trữ dữ liệu <br> - Tạo Data Catalog <br> - Chuyển đổi dữ liệu <br> - Phân tích dữ liệu bằng Athena <br> - Tạo Dashboard với QuickSight <br><br> **Xây dựng Data Lake với dữ liệu của bạn** <br> - Ingestion với Glue <br> - Xây dựng data pipeline <br> - Truy vấn với Athena <br> - Visualization với QuickSight                                                                                                                                                                                                                                                                                                                                                                | 11/03/2025   | 11/03/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | **Các dịch vụ Data Analytics trên AWS** <br> - Thiết kế kiến trúc serverless cho data lakes <br> - Xây dựng data processing pipelines sử dụng Amazon S3 <br> - Sử dụng Amazon Kinesis cho streaming real-time <br> - Sử dụng Amazon Kinesis Data Analytics để phân tích real-time <br> - Sử dụng AWS Glue cho data catalog <br> - Thực hiện Data Transformation <br> - Chạy ETL scripts trên AWS Glue Studio <br> - Sử dụng Glue Studio để chạy và monitoring ETL jobs <br> - Sử dụng Glue DataBrew để chuẩn bị dữ liệu <br> - Chạy Spark transform jobs trên EMR <br> - Upload dữ liệu từ Glue đến Amazon Redshift <br> - Học về best practices của Amazon Redshift <br> - Truy vấn dữ liệu với Athena và visualization với QuickSight | 11/04/2025   | 11/04/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | **Bắt đầu với Amazon QuickSight** <br> - Xây dựng Dashboard <br>&emsp; + Cải thiện Dashboard <br>&emsp; + Dashboard interactivity <br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 11/05/2025   | 11/05/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | **Bắt đầu với Amazon SageMaker** <br> - Feature Engineering <br> - Huấn luyện/Tinh chỉnh/Triển khai XGBoost <br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | 11/06/2025   | 11/06/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | **Tìm hiểu về Amazon Bedrock** <br> - Bedrock Foundation Models <br> - Bedrock API <br> - Xây dựng ứng dụng AI với Bedrock <br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | 11/07/2025   | 11/07/2025      | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 9:

- Thành công trong việc thiết kế và xây dựng kiến trúc Data Lake serverless trên AWS.

- Nắm vững các kỹ thuật thu thập dữ liệu sử dụng AWS Glue cho các hoạt động ETL (Extract, Transform, Load).

- Hiểu và triển khai các best practices lưu trữ dữ liệu sử dụng Amazon S3 làm nền tảng data lake.

- Tạo data catalogs toàn diện sử dụng AWS Glue Data Catalog để khám phá dữ liệu và quản lý metadata.

- Thực hiện chuyển đổi dữ liệu và chuẩn bị dữ liệu sử dụng:

  - AWS Glue cho ETL scripts
  - AWS Glue Studio cho visual ETL job development
  - Glue DataBrew cho data preparation
  - Jupyter notebooks với interactive Glue sessions

- Triển khai streaming dữ liệu real-time sử dụng:

  - Amazon Kinesis để thu thập dữ liệu
  - Amazon Kinesis Data Analytics để phân tích real-time

- Thực hiện các truy vấn phân tích dữ liệu sử dụng Amazon Athena cho serverless SQL queries.

- Tạo các dashboard và visualizations tương tác sử dụng Amazon QuickSight.

- Xử lý big data sử dụng Apache Spark trên Amazon EMR (Elastic MapReduce).

- Tải dữ liệu đã xử lý vào Amazon Redshift data warehouse và học các best practices của Redshift.

- Nắm được kiến thức toàn diện về kiến trúc data lake serverless và các thành phần của nó.

- Hiểu được complete data pipeline từ ingestion đến visualization.

- Thành thạo Amazon QuickSight:

  - Xây dựng dashboards
  - Cải thiện dashboard với visualizations tối ưu
  - Tạo dashboard interactivity

- Bắt đầu với Amazon SageMaker để machine learning:

  - Thực hiện Feature Engineering
  - Huấn luyện, tinh chỉnh và triển khai mô hình XGBoost
  - Hiểu quy trình ML từ chuẩn bị dữ liệu đến deployment

- Tìm hiểu về Amazon Bedrock:

  - Hiểu các Foundation Models có sẵn trên Bedrock
  - Sử dụng Bedrock API để xây dựng ứng dụng AI
  - Tạo các ứng dụng AI generative sử dụng Bedrock
  - Khám phá các use cases của AI và LLM trong AWS

- ...
