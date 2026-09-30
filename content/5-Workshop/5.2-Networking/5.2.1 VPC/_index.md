---
title : "VPC"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 5.2.1 </b> "
---

## Provisioning Virtual Private Cloud (VPC)

**Objective:** Create an isolated virtual network environment on AWS infrastructure to host all game server resources.

## Step-by-Step Implementation

1. Navigate to the **VPC Console** > select **Your VPCs** > click **Create VPC**.

   ![VPC Console](Workshop/images/5/5.2/conVPC.png?featherlight=false&width=90pc)

2. Configure the following parameters:

   - **Name tag**: `game-server-vpc`

   - **IPv4 CIDR block**: `10.0.0.0/16`

   ![Create VPC Configuration](Workshop/images/5/5.2/vpc2.png?featherlight=false&width=90pc)

3. Click **Create VPC**.

   ![VPC Created](Workshop/images/5/5.2/vpc3.png?featherlight=false&width=90pc)