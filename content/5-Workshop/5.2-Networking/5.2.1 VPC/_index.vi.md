---
title : "VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 5.2.1 </b> "
---

## Khởi tạo Virtual Private Cloud (VPC)

**Mục tiêu:** Xây dựng một mạng ảo cô lập hoàn toàn trên hạ tầng AWS để triển khai các tài nguyên của Game Server.

## Thao tác thực hiện

1. Truy cập giao diện **VPC Console** > chọn **Your VPCs** > nhấn **Create VPC**.

![VPC Console](/Workshop/images/5/5.2/conVPC.png)

2. Cấu hình các thông số:

   - **Name tag**: `game-server-vpc`

   - **IPv4 CIDR block**: `10.0.0.0/16` (Cung cấp tối đa 65.536 địa chỉ IP 
   nội bộ).

![Create VPC Configuration](/Workshop/images/5/5.2/vpc2.png)

3. Nhấn **Create VPC**.

![VPC Created](/Workshop/images/5/5.2/vpc3.png)