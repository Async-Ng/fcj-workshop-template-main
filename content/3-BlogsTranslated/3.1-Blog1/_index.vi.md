---
title: "Shield AI và AWS hợp tác để cung cấp khả năng tự chủ nhiệm vụ ở quy mô đội hình"
date: "2025-06-25"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Shield AI và AWS hợp tác để cung cấp khả năng tự chủ nhiệm vụ ở quy mô đội hình

**Tác giả:** Keith Johnson, Tim Wilson và Sean Park | **Ngày:** 25 tháng 6 năm 2025  
**Tags:** Amazon Elastic Container Registry, Announcements, Artificial Intelligence, AWS IoT Core, Defense, Government, Internet of Things, Public Sector

---

## Giới thiệu

Sự phát triển nhanh chóng của các hệ thống tự trị trong quốc phòng và các lĩnh vực khác đang tạo ra những thách thức mới trong triển khai và quản lý phần mềm. Phân tích thị trường nhấn mạnh xu hướng này, với thị trường máy bay không người lái quân sự toàn cầu và xe trên không (UAV) dự kiến sẽ mở rộng với tốc độ tăng trưởng hàng năm ước tính là 11,2% đến 2033.

Sự tăng trưởng đáng kể của UAV quân sự — vốn được xem là đại diện cho thị trường hệ thống tự chủ rộng hơn — làm nổi bật nhu cầu cấp bách về giải pháp triển khai phần mềm có khả năng mở rộng, an toàn và hiệu quả. Khi số lượng nền tảng tự động tăng lên, độ phức tạp trong quản lý phần mềm của chúng cũng tăng. Đáp lại những thách thức này, Shield AI và Amazon Web Services (AWS) đã hợp tác và chứng minh thành công một kiến trúc có khả năng mở rộng và mô hình bằng chứng khái niệm (PoC) để xử lý những vấn đề thường gặp khi triển khai phần mềm tự chủ và các thuật toán máy học lên các hệ thống tự động. Bằng cách tích hợp bộ phát triển phần mềm tự chủ không phụ thuộc nền tảng của Shield AI, Hivemind Enterprise, với AWS IoT Core và Amazon Elastic Container Registry (ECR), các nhà phát triển hệ thống tự chủ có thể phát triển một Hivemind Pilot và — sau khi mô phỏng và thử nghiệm hoàn tất — triển khai trực tiếp lên nền tảng phần cứng mà họ chọn từ đám mây AWS bằng giao diện dòng lệnh (CLI) hoặc giao diện người dùng của Hivemind.

---

## Các thách thức trong triển khai hệ thống tự động

Đối với các khách hàng quốc phòng đưa vào sử dụng hệ thống tự động, việc triển khai phần mềm gặp phải nhiều thách thức, bao gồm:

- **Mở rộng nhiều loại xe**: Hỗ trợ các phương tiện tự trị trên không, đất và biển
- **Hợp tác dành riêng cho nhiệm vụ**: Nhu cầu ngày càng tăng cho sự phối hợp giữa các phương tiện
- **Triển khai nhanh trong môi trường DDIL**: Sự cần thiết phải triển khai nhanh chóng các bản cập nhật trên các đội xe lớn trong môi trường bị từ chối, bị phá vỡ, không liên tục và giới hạn (DDIL)

Những xung đột mới nổi đòi hỏi cập nhật phần mềm và tái cấu hình nhanh chóng giữa các thành phần phần mềm khác nhau của hệ thống. Từ firmware điều khiển tích hợp, mô hình máy học nhiệm vụ, đến các "phi công AI", các bản cập nhật này phải được triển khai một cách an toàn và đáng tin cậy cho các đội hình phương tiện, đảm bảo tính toàn vẹn hệ thống để đối phó với các mối đe dọa và yêu cầu nhiệm vụ thay đổi. Trong khi nhiều khía cạnh của hệ thống phương tiện tự động như phần cứng tiên tiến, cảm biến, điều hướng và nhận thức tự động đã có bước phát triển nhanh, việc cập nhật các hệ thống này thường đòi hỏi quy trình thủ công tốn thời gian, có thể làm chậm phát triển ban đầu và thử nghiệm các khả năng mới, gây ra thắt nút khi thực hiện nhiệm vụ, và tạo cơ hội cho cấu hình sai.

**Liz Martin, Giám đốc điều hành mảng DoD của AWS**, nhấn mạnh tầm quan trọng của sự hợp tác này:

> "Khách hàng quốc phòng của chúng tôi cần các bản cập nhật phần mềm tự chủ nhanh chóng để duy trì trạng thái sẵn sàng và đáp ứng các yêu cầu nhiệm vụ mới nổi. Thông qua sự hợp tác giữa Shield AI và AWS, chúng tôi có một giải pháp cung cấp phát triển và triển khai khả năng tự chủ nhiệm vụ trên quy mô đội hình các nền tảng tự động."

---

## Giải pháp

Sự hợp tác đã giải quyết thách thức cập nhật các hệ thống tự trị bằng cách xây dựng một giải pháp linh hoạt sử dụng AWS IoT Core làm cơ chế có thể mở rộng và bảo mật để điều phối các bản cập nhật và trạng thái giữa các ngăn xếp phần mềm AI Shield (Edgeos) chạy trên nền tảng phần cứng tự trị và nền tảng phát triển tự động của Shield AI. Bởi vì các phi công Hivemind được triển khai dưới dạng container, một khi triển khai mới đã sẵn sàng và truyền đạt qua AWS IoT Core đến nền tảng tự trị, container được lấy một cách an toàn từ Amazon ECR nơi nó được tổ chức bởi Hivemind như là một phần của tích hợp phát triển và triển khai, tạo ra một phương pháp được tổ chức trên đám mây.

Tóm lại, giải pháp cho phép:

- **Kiểm soát tập trung và triển khai nhanh chóng** phần mềm phi công Hivemind
- **Phân phối bảo mật, dựa trên đám mây** cho các hệ thống trường
- **Quản lý có thể mở rộng** các đội tàu tự trị lớn
- **Giám sát thời gian thực và kiểm soát** các quy trình triển khai

**Nathan Michael, Giám đốc công nghệ tại Shield AI** cho biết:

> "Việc phát triển quyền tự chủ vừa phức tạp vừa tốn kém — nhưng với AWS, chúng tôi đang làm cho nó nhanh hơn, dễ dàng hơn và có khả năng mở rộng hơn. Sự hợp tác này kết hợp hệ thống tự chủ Hivemind Enterprise và cơ sở hạ tầng AWS để hợp lý hóa cách khách hàng phát triển, cung cấp và duy trì các hệ thống tự động thông minh trên các nhóm phân tán lớn."

---

## Lợi ích cho khách hàng quốc phòng và thương mại

Sự hợp tác mang lại lợi thế cho cả khách hàng quốc phòng và thương mại. Khách hàng quốc phòng giờ đây có thể duy trì mức độ sẵn sàng thực hiện nhiệm vụ cao bằng cách nhanh chóng cập nhật các hạm đội tự động của họ để chống lại các mối đe dọa mới nổi và thích ứng với các thông số nhiệm vụ thay đổi. Khả năng này đi kèm với sự linh hoạt trong hoạt động tăng lên, cho phép các nhóm nhanh chóng sửa đổi khả năng tự động cho các môi trường và loại nhiệm vụ mới. Giải pháp này cũng tăng cường các biện pháp bảo mật bằng cách đảm bảo tất cả các nền tảng chạy nhất quán các phiên bản phần mềm an toàn, mới nhất, đồng thời cung cấp khả năng quản lý và giám sát tập trung các nền tảng tự trị.

### Ứng dụng thương mại

Trong lĩnh vực thương mại, lợi ích mở rộng trên nhiều ngành:

- **Nông nghiệp**: Các hoạt động nông nghiệp hiện có thể cập nhật hiệu quả đội xe đầu kéo tự hành để thích ứng với sự thay đổi theo mùa và thực hiện các kỹ thuật canh tác mới
- **Dầu khí**: Ngành dầu khí có thể triển khai các bản cập nhật quan trọng cho các hệ thống tự động ngoài khơi, nâng cao cả giao thức an toàn và hiệu quả hoạt động
- **Hậu cần và kho bãi**: Các doanh nghiệp có thể sửa đổi liền mạch đội xe tự hành của họ để thích ứng với các yêu cầu hàng tồn kho và nhu cầu định tuyến ngày càng phát triển
- **Khai thác**: Hoạt động khai thác được hưởng lợi từ khả năng cập nhật nhanh chóng thiết bị tự động để phù hợp với điều kiện địa hình hoặc phương pháp khai thác mới

---

## Kết luận

Sự hợp tác giữa Shield AI và AWS giải quyết một thách thức quan trọng trong quản lý hệ thống tự động. Bằng cách chứng minh việc triển khai phần mềm tự chủ nhiệm vụ nhanh chóng, an toàn, chúng tôi đang cho phép các tổ chức trong lĩnh vực quốc phòng và thương mại tận dụng tối đa sức mạnh của đội xe tự động của họ. Sự tích hợp này cũng thiết lập nền tảng cho việc thu thập dữ liệu sau nhiệm vụ, điều này rất quan trọng để thúc đẩy sự phát triển phi công nhanh chóng và cải thiện liên tục các khả năng tự động. Trong giai đoạn tiếp theo của quá trình hợp tác, chúng tôi đang chuyển từ bằng chứng khái niệm sang sản xuất và chúng tôi rất vui mừng được khám phá cách giải pháp này sẽ chuyển đổi hoạt động và mở ra những khả năng mới trong quyền tự chủ.

---

## Về tác giả

### Keith Johnson

Keith là giám đốc kỹ thuật cho hoạt động kinh doanh của Bộ Quốc phòng Hoa Kỳ (DoD) của AWS. Keith lãnh đạo một nhóm kiến trúc sư giải pháp giàu kinh nghiệm, những người hoạt động với tư cách là cố vấn kỹ thuật đáng tin cậy cho khách hàng của DoD, hướng dẫn họ tối đa hóa kết quả kinh doanh và sứ mệnh bằng cách tận dụng các giải pháp và phương pháp thực hành tốt nhất của AWS. Keith gia nhập AWS vào tháng 5 năm 2022.

### Tim Wilson

Tim là chuyên gia IoT chính của nhóm Chuyên gia Liên bang Hoa Kỳ của AWS. Trong vai trò này, Tim làm việc với các khách hàng và đối tác của AWS Liên bang Hoa Kỳ để hỗ trợ họ áp dụng và sử dụng các dịch vụ và giải pháp AWS IoT. Anh bắt đầu làm việc tại AWS với tư cách là kiến trúc sư giải pháp vào năm 2012.

### Sean Park

Sean là giám đốc điều hành khách hàng chính tại AWS, hỗ trợ Bộ Quốc phòng (DoD) và thúc đẩy các khả năng quan trọng sáng tạo với các đối tác. Ngoài công việc, anh ấy thích tìm kiếm những cuộc phiêu lưu ẩm thực mới với vợ và hai con.
