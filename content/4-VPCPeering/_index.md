---
title : "Create Peering Connection"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Create a peering connection

In the bounce, you will create a **VPC Peering** (**VPC Peering Connection**) connection between **My VPC and HG VPC**.

1. Login to **AWS Management Console**

   - Find **VPC**
   - Select **VPC**

![Create VPC Peering](/images/4/1.png?featherlight=false&width=90pc)

2. In **VPC Management Console***, navigate to **Peering Connections**. Then, click **Create Peering Connection.**

![Create VPC Peering](/images/4/2.png?featherlight=false&width=90pc)

3. On the **Create Peering Connection** page, enter the following parameters and then select **Create Peering Connection**:
   - **Peering connection name tag**: lab-vpc-peer
   - **VPC (Requester)**: select My VPC

![Create VPC Peering](/images/4/3.png?featherlight=false&width=90pc)

4. For **Select another VPC to peer with**

   - **Account**: choose **My account** because the 2 VPCs in **peering connection** are in the same **account**
   - **Region**: choose **This region (ap-southeast-1)** because the 2 VPCs in the peering connection are in the same region.
   - **VPC (Accepter)**: HG VPC

![Create VPC Peering](/images/4/4.png?featherlight=false&width=90pc)

5. Complete **Create Peering Connection**

![Create VPC Peering](/images/4/5.png?featherlight=false&width=90pc)

6. On the information page of **Peering Connections**, tick **VPC Peering** just created then click **Actions** and **Accept Request**.

![Create VPC Peering](/images/4/6.png?featherlight=false&width=90pc)
![Create VPC Peering](/images/4/7.png?featherlight=false&width=90pc)

7. Select **Accept request**

![Create VPC Peering](/images/4/8.png?featherlight=false&width=90pc)

8. Setup was successful.

![Create VPC Peering](/images/4/9.png?featherlight=false&width=90pc)

9. From **EC2 - My VPC**, try pinging **private IP** of **EC2 - HG VPC**. Ping still fails because we haven't configured the VPC router to route traffic between the 2 VPCs.

![Create VPC Peering](/images/4/10.png?featherlight=false&width=90pc)