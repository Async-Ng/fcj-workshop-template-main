---
title: "Event 1"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “AI-Driven Development Life Cycle”

### Mục Đích Của Sự Kiện

- Giới thiệu mô hình AI-Driven Development Life Cycle (AI-DLC): Tái định hình cách phát triển phần mềm từ lập kế hoạch, phát triển, kiểm thử đến vận hành.
- Hướng dẫn cách tự động hóa các công việc nặng nhọc không tạo ra giá trị khác biệt (undifferentiated heavy lifting) để tập trung vào các tác vụ sáng tạo giá trị cao.
- Trình diễn thực tế việc ứng dụng Amazon Q Developer và Kiro trong quy trình phát triển phần mềm hiện đại.

### Danh Sách Diễn Giả

- **Toàn Huỳnh** – Instructor (Trình bày về AI-DLC & Amazon Q Developer)
- **Mỹ Nguyễn** – Instructor (Demo công cụ Kiro)
- **Địa điểm**: AWS Event Hall, Tầng 26 Tháp Bitexco, TP.HCM

### Nội Dung Nổi Bật

#### Sự phát triển: Từ Trợ lý Code đến AI Agents (2023-2025)

- 2023 (Auto-Complete): Hỗ trợ viết code nhanh hơn.
- 2024 (Assistants): Tạo các đoạn code lớn, trả lời câu hỏi kỹ thuật.
- 2025 (Agents): Hoàn thành các tác vụ đầu-cuối (End-to-End) với sự giám sát của con người (Human-in-the-loop).

#### Khái niệm cốt lõi: AI-Driven Development (AI-DLC)

Phân biệt các mô hình phát triển:

- **AI-Assisted**: AI chỉ hỗ trợ các tác vụ hẹp, con người vẫn làm phần lớn công việc trí tuệ.
- **AI-Managed**: AI tự chủ hoàn toàn (chưa phổ biến).
- **AI-Driven** (Trọng tâm): AI đóng vai trò điều phối (orchestrator) quy trình phát triển, đưa ra kế hoạch và kiến trúc. Con người giữ vai trò xác thực (Validation) và ra quyết định cuối cùng.

#### Quy trình chuẩn: Spec-Driven Development (Phát triển dựa trên đặc tả)

Quy trình làm việc chuẩn được giới thiệu trong phiên của diễn giả Toàn Huỳnh:

- **Inception (Khởi tạo)**: Xây dựng User Stories, lập kế hoạch (plan.md), và làm rõ yêu cầu với AI đóng vai Product Manager.
- **Construction (Xây dựng)**: AI thực hiện tạo Domain Model, sinh code, viết Test và IaaC (Infrastructure as Code).
- **Operation (Vận hành)**: Triển khai và quản lý sự cố.

#### Hệ sinh thái công cụ: Amazon Q Developer & Kiro

Buổi workshop tập trung vào demo hai công cụ chính:

- **Amazon Q Developer**: Trợ lý AI hỗ trợ toàn bộ vòng đời SDLC, giúp tự động hóa các tác vụ lặp lại, nâng cấp code (code transformation) và bảo mật ứng dụng.
- **Kiro**: Công cụ Agentic AI được demo bởi diễn giả Mỹ Nguyễn, thể hiện khả năng thực thi các tác vụ phức tạp trong quy trình AI-Driven, giúp lập trình viên giảm tải các công việc thủ công.

#### Các sai lầm cần tránh (Anti-Patterns)

Những lỗi phổ biến khi làm việc với AI:

- **Single-shot Prompts**: Cố gắng giải quyết vấn đề lớn/phức tạp chỉ bằng một câu lệnh duy nhất.
- **Context Overload:** Không làm mới ngữ cảnh khi hội thoại quá dài, dẫn đến AI bị "loãng" thông tin.
- **Lack of Guidance**: Để AI tự quyết định quá nhiều mà không có sự kiểm soát phạm vi (Over-reach).

### Những Gì Học Được

#### Tư duy thiết kế (Design Mindset)

- **Tái định hình kỹ sư phần mềm**: Chuyển đổi tư duy từ "người viết code" (Coder) sang "người kiến tạo và xác thực" (Architect & Validator).

- **Tập trung vào nghiệp vụ**: Tự động hóa giúp Developer tập trung vào logic nghiệp vụ và sáng tạo thay vì cấu hình hạ tầng lặp đi lặp lại.

#### Kiến trúc kỹ thuật

- **Prompt as Code**: Sử dụng các "Mẫu Prompt" chuẩn (ví dụ: đóng vai Expert Product Manager) để tạo ra các bản kế hoạch và tài liệu chất lượng cao.

- **Spec-Driven**: Bắt buộc có tài liệu/kế hoạch rõ ràng (như file .md) trước khi bắt tay vào code để AI hiểu đúng ngữ cảnh.

#### Chiến lược hiện đại hóa

- Áp dụng **Amazon Q Developer** để xử lý các tác vụ "undifferentiated heavy lifting" (công việc tốn sức nhưng ít giá trị gia tăng).

- Tích hợp các AI Agents như **Kiro** để thực hiện các luồng công việc tự động hóa cao hơn (Agentic Workflows).

#### Ứng dụng vào công việc

- **Triển khai AI-DLC**: Bắt đầu áp dụng quy trình Inception -> Construction với sự hỗ trợ của AI cho dự án sắp tới.

- **Sử dụng Amazon Q Developer**: Tích hợp vào IDE (VS Code, IntelliJ) để hỗ trợ hoàn thành code, giải thích code và vá lỗi bảo mật.

- **Thử nghiệm Kiro**: Đánh giá khả năng của Kiro trong việc giải quyết các bài toán cụ thể của dự án để tăng năng suất.

- **Tối ưu hóa Prompt**: Áp dụng mẫu prompt lập kế hoạch (Plan-first) để tránh việc AI tạo code sai hướng hoặc thiếu ngữ cảnh.

### Trải nghiệm trong event

Tham gia buổi sinh hoạt của AWS GenAI Builder Club tại tháp Bitexco là một trải nghiệm rất giá trị:

#### Học hỏi từ chuyên gia

- Phần trình bày của Anh Toàn Huỳnh đã giúp tôi hệ thống hóa lại kiến thức về sự phát triển của AI, từ Auto-complete đơn giản đến mô hình Agent phức tạp trong năm 2025.

- Phần demo thực tế về Kiro của Chị Mỹ Nguyễn rất ấn tượng, cho thấy tiềm năng thực sự của AI Agents trong việc xử lý các tác vụ lập trình đầu-cuối.

#### Tầm nhìn tương lai

- Tôi nhận ra rằng việc nắm vững Amazon Q Developer và các công cụ như Kiro không còn là lựa chọn mà là yêu cầu bắt buộc để duy trì lợi thế cạnh tranh của một lập trình viên trong kỷ nguyên AI sắp tới.
