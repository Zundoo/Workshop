---
title: "Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: true
pre: " <b> 1. </b> "
---

# AWS Real-time Game Server Workshop

## Tổng quan Lab

Workshop này tập trung vào quy trình thiết kế, triển khai và kiểm thử hạ tầng cloud dành cho **Real-time Game Server** hoạt động trên kết nối **WebSocket** bền vững.

Workshop sử dụng hệ sinh thái **Amazon Web Services (AWS)** kết hợp với các công nghệ containerization, networking, bảo mật, database, load balancing, giám sát và tự động mở rộng để xây dựng một hạ tầng game server đáng tin cậy và có khả năng mở rộng.

![Overall AWS Game Server Architecture Diagram](/images/architecture-diagram.png)

{{% notice info %}}
**Lưu ý về Bảo mật:**

Hạ tầng được thiết kế theo mô hình **3-Tier Architecture** nhằm tách biệt lớp truy cập công khai, lớp ứng dụng và lớp dữ liệu.

Các tài nguyên tiếp xúc với Internet được đặt trong Public Subnets, trong khi ứng dụng và database được cô lập trong Private Subnets.
{{% /notice %}}

## Các dịch vụ AWS chính

- **Amazon VPC**: Xây dựng mạng ảo cô lập, cấu hình subnet, route table và bảo mật mạng.
- **AWS IAM**: Quản lý người dùng, vai trò, quyền hạn và cơ chế xác thực để bảo vệ tài nguyên AWS.
- **Amazon ECR & Docker**: Xây dựng, đóng gói container và lưu trữ image của ứng dụng Game Server.
- **Amazon ECS**: Điều phối các ứng dụng Game Server dạng container bằng AWS Fargate.
- **Application Load Balancer (ALB)**: Cung cấp điểm truy cập công khai và phân phối kết nối WebSocket đến các container Game Server.
- **Amazon ElastiCache for Redis**: Cung cấp lớp dữ liệu in-memory độ trễ thấp để chia sẻ session và trạng thái real-time của game.
- **Amazon CloudWatch**: Thu thập metric ứng dụng & hạ tầng và quản lý log container tập trung.

## Mục tiêu Workshop

Sau khi hoàn thành workshop, bạn sẽ học được cách:

1. Thiết kế kiến trúc mạng AWS an toàn và có khả năng mở rộng.
2. Cấu hình IAM và các cơ chế xác thực cho tài nguyên AWS.
3. Triển khai WebSocket Game Server dạng container bằng Amazon ECS và AWS Fargate.
4. Cấu hình Redis làm lớp dữ liệu in-memory cho ứng dụng real-time.
5. Công khai Game Server thông qua Application Load Balancer.
6. Cấu hình tự động mở rộng dựa trên mức sử dụng tài nguyên của ứng dụng.
7. Giám sát hiệu năng ứng dụng và log container bằng Amazon CloudWatch.
8. Thực hiện load testing để đánh giá Game Server dưới tải kết nối đồng thời cao.

## Điều hướng các phần thực hiện

1. [1.1 Week 1 – Worklog](1.1-Week-1-Worklog/)
2. [1.2 Week 2 – Worklog](1.2-Week-2-Worklog/)
3. [1.3 Week 3 – Worklog](1.3-Week-3-Worklog/)
4. [1.4 Week 4 – Worklog](1.4-Week-4-Worklog/)
5. [1.5 Week 5 – Worklog](1.5-Week-5-Worklog/)
6. [1.6 Week 6 – Worklog](1.6-Week-6-Worklog/)
7. [1.7 Week 7 – Worklog](1.7-Week-7-Worklog/)
8. [1.8 Week 8 – Worklog](1.8-Week-8-Worklog/)