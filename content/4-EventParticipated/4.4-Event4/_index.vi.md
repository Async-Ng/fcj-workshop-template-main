---
title: "Báo cáo tóm tắt: Workshop Bảo mật Mạng và Kiến trúc AWS"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Báo cáo tóm tắt: "Workshop Bảo mật Mạng và Kiến trúc AWS"

## Mục đích sự kiện

- Hiểu sự khác biệt giữa các công nghệ MFA (TOTP vs. FIDO2).
- Xác định các vector tấn công mạng phổ biến (Ingress, Egress, và Inside attacks).
- Học cách triển khai bảo mật đa lớp bằng các dịch vụ AWS như WAF, Shield, Network Firewall, và Security Groups.
- Thiết kế luồng traffic "tốt" bằng Transit Gateways và các điểm egress tập trung.

## Diễn giả

## Nội dung nổi bật

### Sự tiến hóa của Xác thực đa yếu tố (MFA)

- **TOTP (Time-based One-Time Password)**: Phụ thuộc vào bí mật chia sẻ và yêu cầu nhập thủ công mã 6 chữ số. Nó miễn phí và cung cấp sao lưu linh hoạt.
- **FIDO2**: Sử dụng mật mã khóa công khai và yêu cầu chạm đơn giản hoặc quét sinh trắc học. Nó hỗ trợ các trình xác thực biến đổi và thực thi sao lưu nghiêm ngặt.

### Hiểu về Vector Tấn công

- **Tấn công Ingress**: Các mối đe dọa từ internet, chẳng hạn như tấn công DDoS, tấn công ứng dụng (SQL injection, XSS), và hoạt động Bot.
- **Tấn công Inside**: Các mối đe dọa trong mạng, bao gồm chuyển động ngang giữa các dịch vụ và lan truyền phần mềm độc hại.
- **Tấn công Egress**: Các mối đe dọa cố gắng rời khỏi mạng, chẳng hạn như tunneling DNS hoặc exfiltration dữ liệu.

### Phòng thủ theo chiều sâu (Bảo mật đa lớp)

- **Bảo vệ Edge**: Sử dụng **CloudFront, WAF, và Shield** để ngăn chặn DDoS, tường lửa ứng dụng, kiểm soát bot, và phát hiện gian lận.
- **Kiểm soát Mạng & Tài nguyên**: Triển khai **Security Groups & NACLs** để kiểm soát cấp tài nguyên và cấp mạng chống lại chuyển động ngang.
- **Traffic Đông-Tây**: Sử dụng **Network Firewalls** (IPS/IDS) để kiểm soát luồng traffic giữa các VPC.
- **Bảo mật DNS**: Triển khai **Route 53 DNS Firewall** để lọc tên miền và chặn truy cập vào các trang web độc hại.

### Kiến trúc & Luồng Traffic

- **Định tuyến Traffic**: Sử dụng **Transit Gateway** với các phân đoạn định tuyến để quản lý các kết nối phức tạp giữa Production và Project VPCs.
- **Egress Tập trung**: Thiết lập VPC "Central Internet Egress" để lọc và giám sát tất cả traffic outbound qua Web Proxy hoặc Firewall.
- **Phân đoạn**: Tách biệt các môi trường (ví dụ: Prod, Project A, Project B) thành các subnet riêng biệt (Web/App, DB) để chứa các vi phạm tiềm ẩn.

## Những gì học được

### Chiến lược Bảo mật

- **Phòng thủ Lớp**: Bảo mật phải được áp dụng ở nhiều lớp—Edge, Mạng, và Host—để giảm thiểu hiệu quả các loại vector tấn công khác nhau.
- **Identity First**: Chuyển sang các phương pháp xác thực mạnh hơn như FIDO2 để bảo mật tốt hơn và trải nghiệm người dùng so với TOTP truyền thống.

### Các Thực tiễn Kiến trúc Tốt nhất

- **Tập trung hóa**: Sử dụng Transit Gateways để tập trung định tuyến và đơn giản hóa quản lý mạng trên nhiều VPC.
- **Tầm nhìn**: Triển khai các kiểm soát cụ thể như DNS Firewalls và Network Firewalls cung cấp tầm nhìn vào traffic nội bộ (Đông-Tây) và outbound, không chỉ các yêu cầu đến.

## Ứng dụng vào công việc

- **Xem xét Chính sách MFA**: Đánh giá khả năng chuyển từ TOTP sang khóa phần cứng FIDO2 hoặc sinh trắc học cho các tài khoản đặc quyền.
- **Kiểm tra Security Groups**: Xem xét các Security Groups và NACLs hiện tại để đảm bảo chúng được định nghĩa nghiêm ngặt nhằm ngăn chặn chuyển động ngang.
- **Triển khai WAF**: Triển khai AWS WAF trên Application Load Balancers (ALB) hoặc API Gateways công khai để chặn các khai thác web phổ biến.
- **Phân đoạn Mạng**: Đánh giá kiến trúc VPC hiện tại và xem xét triển khai Transit Gateway nếu quản lý nhiều VPC để đảm bảo luồng traffic "tốt".

## Trải nghiệm trong sự kiện

Tham gia workshop **"AWS Network Security & Architecture"** cung cấp hướng dẫn trực quan rõ ràng về bảo mật cơ sở hạ tầng đám mây. Các trải nghiệm chính bao gồm:

### Hình dung các Lớp Bảo mật

- Các sơ đồ minh họa rõ ràng cách các dịch vụ AWS khác nhau (WAF, Shield, Network Firewall) ánh xạ đến các vector tấn công cụ thể như DDoS hoặc SQL injection.
- Thật có giá trị khi thấy sự phân biệt giữa bảo vệ chống lại các tấn công "Ingress" so với chuyển động ngang "Inside".

### Hiểu về Xác thực Hiện đại

- Sự so sánh trực tiếp giữa TOTP và FIDO2 làm nổi bật sự đánh đổi giữa tiện lợi (chạm/sinh trắc học) và các phương pháp truyền thống (nhập mã).

### Đào sâu Kiến trúc

- Xem sơ đồ "Good Traffic Flows" giúp làm rõ cách kiến trúc mạng cấp sản xuất bằng Transit Gateways và các điểm egress internet tập trung.

### Một số hình ảnh sự kiện

> Tổng thể, phiên làm tăng cường tầm quan trọng không chỉ của bảo mật perimeter, mà còn của phân đoạn mạng nội bộ và quản lý danh tính mạnh mẽ.
