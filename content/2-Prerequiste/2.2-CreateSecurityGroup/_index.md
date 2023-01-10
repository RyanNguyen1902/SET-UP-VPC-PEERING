---
title : "Create Security Group"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create Security Group

This step will detail how to create **My VPC SG** using **CloudFormation Template**. You can repeat this step to create more **HG VPC SG**.

To determine which **Inbound** rules are required, list the requirements as follows:

You can connect **SSH to your EC2 instance** with the source as your IP.
- Two **EC2 instances** in two VPCs can be pinged via the ICMP - IPv4 protocol with the source being Anywhere.
- Two **EC2 instances** in two VPCs can ping each other using the **ICMP - IPv4** protocol with the source being the CIDR of the other VPC.

1. Access the AWS Management Console. Select Services in the navigation bar and search for **VPC** service.


![Create Security Group](/images/2.2/17.png?featherlight=false&width=90pc)

2. In the **VPC** interface

   - In the left navigation bar, select **Security Groups**.
   - On the **Security Groups** page, select **Create Security Group**.

![Create Security Group](/images/2.2/18.png?featherlight=false&width=90pc)

3. On the Create security group page, set the following parameters:
   - Section **Basic details**:
     - **Security group name**: Enter the security group name (eg: MY VPC SG)
     - **Description**: Enter the description of the security group.
     - **VPC**: Select My VPC

![Create Security Group](/images/2.2/19.png?featherlight=false&width=90pc)

4. Inbound rules section: Add Inbound rules as mentioned above. Select Add rule to add a rule.
   - **Type**: SSH | **Source**: My IP
   - **Type**: All ICMP - IPv4 | **Source**: Anywhere
   - **Type**: All ICMP - IPv4 | **Source**: Custom 10.10.0.0/16 (HG VPC's CIDR)

![Create Security Group](/images/2.2/20.png?featherlight=false&width=90pc)

5. Select **Create security group**.

![Create Security Group](/images/2.2/21.png?featherlight=false&width=90pc)

6. Create **Security Group** successfully.

![Create Security Group](/images/2.2/22.png?featherlight=false&width=90pc)

7. Repeat the steps to create **HG VPC SG** as follows:

   - Section **Basic details**:
     - **Security group name**: Enter the security group name (eg HG VPC SG)
     - **Description**: Enter the description of the security group.
     - **VPC**: Select HG VPC


![Create Security Group](/images/2.2/23.png?featherlight=false&width=90pc)

8. Section **Inbound rules**: Add Inbound rules as mentioned above. Select Add rule to add a rule.
   - **Type**: SSH | Source: My IP
   - **Type**: All ICMP - IPv4 | Source: Anywhere
   - **Type**: All ICMP - IPv4 | Source: Custom 172.31.0.0/16 (My VPC's CIDR)


![Create Security Group](/images/2.2/24.png?featherlight=false&width=90pc)

9. Select **Create security group**.

![Create Security Group](/images/2.2/25.png?featherlight=false&width=90pc)

10. Create **Security group** successfully.

![Create Security Group](/images/2.2/26.png?featherlight=false&width=90pc)