---
title : "Proposal"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2 </b> "
---

# Project Proposal  
## AWS Real-time Game Server

### 1. Project Title

**Building a Scalable Real-time Game Server on AWS**

### 2. Project Overview

This project aims to design and deploy a **real-time multiplayer Game Server** on Amazon Web Services (AWS). The system supports persistent WebSocket connections, low-latency communication, and horizontal scaling to handle fluctuating player loads.

The solution leverages managed AWS services to ensure high availability, security, and operational simplicity while remaining cost-effective for workshop and production use cases.

### 3. Objectives

- Deploy a real-time Game Server that supports **WebSocket** connections for multiplayer gameplay.
- Design a secure network architecture using **VPC, Public/Private Subnets, Security Groups, NAT Gateway, and Internet Gateway**.
- Containerize the Game Server application using **Docker** and orchestrate it with **Amazon ECS (Fargate)**.
- Store persistent game data in **Amazon RDS (MySQL)** and manage real-time session state with **Amazon ElastiCache (Redis)**.
- Distribute traffic using an **Application Load Balancer (ALB)** with health checks.
- Implement **Auto Scaling** to automatically adjust the number of Game Server tasks based on CPU utilization.
- Enable monitoring and observability through **Amazon CloudWatch Logs**.
- Validate system performance through **HTTP health checks** and **WebSocket load testing** (Artillery).

### 4. Scope of Work

| Area                    | Description                                              |
|-------------------------|----------------------------------------------------------|
| Networking              | VPC, Subnets, Route Tables, Internet Gateway, NAT Gateway, Security Groups |
| Compute & Containers    | ECS Cluster, Task Definition, ECS Service (Fargate)      |
| Database & Cache        | Amazon RDS (MySQL), Amazon ElastiCache (Redis)           |
| Load Balancing          | Application Load Balancer, Target Group, Health Checks   |
| Scaling                 | ECS Service Auto Scaling (CPU-based)                     |
| Monitoring              | CloudWatch Logs                                          |
| Load Testing            | HTTP Health Check + WebSocket Stress Test (Artillery)    |

### 5. High-Level Architecture

```text
Users
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
  ├──► Amazon RDS (MySQL) – Persistent data
  └──► ElastiCache Redis – Session & real-time state