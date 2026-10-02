---
title : "Proposal"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2 </b> "
---

# Đề xuất Dự án  
## AWS Real-time Game Server

### 1. Tên dự án

**Xây dựng Hệ thống Game Server Real-time có khả năng mở rộng trên AWS**

### 2. Tổng quan dự án

Dự án nhằm thiết kế và triển khai một **Game Server multiplayer real-time** trên nền tảng Amazon Web Services (AWS). Hệ thống hỗ trợ kết nối WebSocket bền vững, giao tiếp độ trễ thấp và có khả năng mở rộng theo chiều ngang để xử lý tải người chơi biến động.

Giải pháp tận dụng các dịch vụ quản lý của AWS nhằm đảm bảo tính sẵn sàng cao, bảo mật và dễ vận hành, đồng thời vẫn tối ưu chi phí cho mục đích workshop cũng như môi trường thực tế.

### 3. Mục tiêu

- Triển khai Game Server real-time hỗ trợ kết nối **WebSocket** cho trò chơi multiplayer.
- Thiết kế kiến trúc mạng bảo mật sử dụng **VPC, Public/Private Subnets, Security Groups, NAT Gateway và Internet Gateway**.
- Đóng gói ứng dụng Game Server bằng **Docker** và điều phối bằng **Amazon ECS (Fargate)**.
- Lưu trữ dữ liệu game bền vững trên **Amazon RDS (MySQL)** và quản lý trạng thái phiên real-time bằng **Amazon ElastiCache (Redis)**.
- Phân phối lưu lượng truy cập thông qua **Application Load Balancer (ALB)** kèm health check.
- Triển khai **Auto Scaling** để tự động điều chỉnh số lượng task Game Server dựa trên CPU utilization.
- Giám sát hệ thống thông qua **Amazon CloudWatch Logs**.
- Kiểm thử hiệu năng bằng **HTTP health check** và **WebSocket load testing** (Artillery).

### 4. Phạm vi công việc

| Lĩnh vực                | Mô tả                                                        |
|-------------------------|--------------------------------------------------------------|
| Networking              | VPC, Subnets, Route Tables, Internet Gateway, NAT Gateway, Security Groups |
| Compute & Containers    | ECS Cluster, Task Definition, ECS Service (Fargate)          |
| Database & Cache        | Amazon RDS (MySQL), Amazon ElastiCache (Redis)               |
| Load Balancing          | Application Load Balancer, Target Group, Health Checks       |
| Scaling                 | ECS Service Auto Scaling (dựa trên CPU)                      |
| Monitoring              | CloudWatch Logs                                              |
| Load Testing            | HTTP Health Check + WebSocket Stress Test (Artillery)        |

### 5. Kiến trúc tổng quan

```text
Người dùng (Users)
  │
  ▼
Application Load Balancer (Internet-facing)
  │
  ▼
Target Group (Port 8080)
  │
  ▼
ECS Fargate Tasks (Game Server)
  │
  ├──► Amazon RDS (MySQL) – Dữ liệu bền vững
  └──► ElastiCache Redis – Session & trạng thái real-time