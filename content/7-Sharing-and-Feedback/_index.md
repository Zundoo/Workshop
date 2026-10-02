---
title : "Sharing and Feedback"
date : "`r Sys.Date()`"
weight : 11
chapter : false
pre : " <b> 11 </b> "
---

# Sharing and Feedback

### 1. Knowledge Sharing

Throughout this workshop, I actively shared knowledge and experiences with teammates and instructors in the following ways:

- Explained the design of the VPC architecture (Public/Private Subnets, NAT Gateway, Route Tables) and the rationale behind placing the Game Server, RDS, and Redis in private networks.
- Shared troubleshooting experiences related to:
  - SSM Agent connection issues
  - Redis connection timeouts caused by Security Group misconfiguration
  - RDS authentication and Secrets Manager permissions
- Demonstrated how to containerize the WebSocket Game Server with Docker and deploy it on Amazon ECS (Fargate).
- Shared the Artillery load testing configuration and CloudWatch Logs analysis results.

### 2. Collaboration Experience

Working on this project provided valuable collaboration experience:

- Coordinated with team members to align on architecture decisions (ECS vs EC2, MySQL vs PostgreSQL, etc.).
- Discussed trade-offs between cost optimization (Free Tier / t3.micro) and production readiness (Multi-AZ, Auto Scaling).
- Reviewed and improved Security Group rules together to follow the least-privilege principle.
- Exchanged feedback on documentation structure and clarity of the workshop report.

### 3. Feedback Received

| Feedback Source       | Content                                                                 | Action Taken                          |
|-----------------------|-------------------------------------------------------------------------|---------------------------------------|
| Instructor            | Should emphasize the difference between Public and Private Subnets more clearly | Updated networking documentation      |
| Teammate              | Health check path should be `/health` instead of `/`                    | Corrected Target Group configuration  |
| Self-review           | Missing detailed explanation of Auto Scaling cooldown behavior          | Added clarification in Scaling section |
| Peer review           | Architecture diagram should include CI/CD and Monitoring components     | Updated Overall Architecture diagram  |

### 4. Feedback Given to Others

- Suggested improving Security Group documentation by clearly listing inbound/outbound rules for each component.
- Recommended adding a troubleshooting section for common connection issues (SSM, Redis, RDS).
- Proposed standardizing image file naming conventions in the documentation for better maintainability.
- Encouraged teammates to test WebSocket connections early to detect networking issues sooner.

### 5. Lessons from Sharing & Feedback

- Clear documentation and diagrams significantly reduce misunderstanding within the team.
- Early and frequent feedback helps catch configuration mistakes before they become costly.
- Explaining technical decisions to others deepens one’s own understanding of the system.
- Combining practical troubleshooting stories with architecture explanations makes knowledge sharing more effective.

### 6. Conclusion

The sharing and feedback process played an important role in improving both the quality of the system and the clarity of the project documentation. Open communication and constructive reviews helped the team deliver a more complete and reliable Real-time Game Server on AWS.