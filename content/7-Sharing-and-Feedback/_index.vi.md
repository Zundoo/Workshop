---
title : "Sharing and Feedback"
date : "`r Sys.Date()`"
weight : 11
chapter : false
pre : " <b> 11 </b> "
---

# Chia sẻ và Phản hồi  
## Sharing and Feedback

### 1. Chia sẻ kiến thức

Trong suốt quá trình thực hiện workshop, tôi đã chủ động chia sẻ kiến thức và kinh nghiệm với các thành viên trong nhóm cũng như giảng viên thông qua các nội dung sau:

- Giải thích thiết kế kiến trúc VPC (Public/Private Subnets, NAT Gateway, Route Tables) và lý do đặt Game Server, RDS, Redis trong mạng riêng (Private Subnet).
- Chia sẻ kinh nghiệm xử lý sự cố liên quan đến:
  - Lỗi kết nối SSM Agent
  - Timeout khi kết nối Redis do cấu hình Security Group sai
  - Lỗi xác thực RDS và quyền truy cập Secrets Manager
- Hướng dẫn cách đóng gói WebSocket Game Server bằng Docker và triển khai trên Amazon ECS (Fargate).
- Chia sẻ cấu hình load testing bằng Artillery và cách phân tích log trên CloudWatch.

### 2. Kinh nghiệm làm việc nhóm

Việc thực hiện dự án này mang lại nhiều kinh nghiệm làm việc nhóm có giá trị:

- Phối hợp với các thành viên để thống nhất quyết định kiến trúc (ECS hay EC2, MySQL hay PostgreSQL…).
- Thảo luận về sự đánh đổi giữa tối ưu chi phí (Free Tier / t3.micro) và mức độ sẵn sàng cho môi trường production (Multi-AZ, Auto Scaling).
- Cùng nhau rà soát và cải thiện quy tắc Security Group theo nguyên tắc least privilege.
- Trao đổi phản hồi về cấu trúc tài liệu và mức độ rõ ràng của báo cáo workshop.

### 3. Phản hồi nhận được

| Nguồn phản hồi     | Nội dung phản hồi                                                      | Hành động đã thực hiện                     |
|--------------------|------------------------------------------------------------------------|--------------------------------------------|
| Giảng viên         | Cần nhấn mạnh rõ hơn sự khác biệt giữa Public và Private Subnet        | Cập nhật phần tài liệu Networking          |
| Thành viên nhóm    | Health check path nên dùng `/health` thay vì `/`                       | Chỉnh lại cấu hình Target Group            |
| Tự đánh giá        | Thiếu giải thích chi tiết về hành vi cooldown của Auto Scaling         | Bổ sung làm rõ trong phần Scaling          |
| Đánh giá ngang hàng| Sơ đồ kiến trúc nên bao gồm thêm CI/CD và Monitoring                   | Cập nhật Overall Architecture Diagram      |

### 4. Phản hồi đã đưa cho người khác

- Đề xuất cải thiện phần tài liệu Security Group bằng cách liệt kê rõ ràng inbound/outbound rules cho từng thành phần.
- Khuyến nghị bổ sung mục Troubleshooting cho các lỗi kết nối phổ biến (SSM, Redis, RDS).
- Đề xuất chuẩn hóa quy ước đặt tên file ảnh trong tài liệu để dễ bảo trì hơn.
- Khuyến khích các thành viên kiểm tra kết nối WebSocket sớm để phát hiện lỗi mạng kịp thời.

### 5. Bài học từ việc chia sẻ và phản hồi

- Tài liệu và sơ đồ rõ ràng giúp giảm đáng kể sự hiểu nhầm trong nhóm.
- Phản hồi sớm và thường xuyên giúp phát hiện lỗi cấu hình trước khi chúng trở nên nghiêm trọng.
- Việc giải thích quyết định kỹ thuật cho người khác giúp bản thân hiểu sâu hơn về hệ thống.
- Kết hợp câu chuyện xử lý sự cố thực tế với phần giải thích kiến trúc giúp việc chia sẻ kiến thức hiệu quả hơn.

### 6. Kết luận

Quá trình chia sẻ và phản hồi đóng vai trò quan trọng trong việc nâng cao chất lượng hệ thống cũng như sự rõ ràng của tài liệu dự án. Sự giao tiếp cởi mở và các đánh giá mang tính xây dựng đã giúp nhóm hoàn thiện tốt hơn hệ thống Real-time Game Server trên AWS.