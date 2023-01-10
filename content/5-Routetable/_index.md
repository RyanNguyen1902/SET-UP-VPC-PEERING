---
title : "Configuring Route tables"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Configure Route tables


1. Login **AWS Management Console**

   - Find **VPC**
   - Select **VPC**

![Configure Route Table](/images/5/1.png?featherlight=false&width=90pc)

2. Go to **VPC Management Console**, and select **Route tables** in the left sidebar.


![Configure Route Table](/images/5/2.png?featherlight=false&width=90pc)

3. Tick the routeing table **My VPC Pubilc Routes**, select the **Routes** tab on the screen below, and select **Edit routes**

![Configure Route Table](/images/5/3.png?featherlight=false&width=90pc)

4. Select Add route. Under the **Destination** column, enter **10.10.0.0/16**. Under the **Target** column, select the **Peering connection** that we created.

![Configure Route Table](/images/5/4.png?featherlight=false&width=90pc)

5. Click **Save changes**. Thus, you have directed the queries for block **10.10.0.0/16** (HG VPC's CIDR) to **Peering connection** that you created

![Configure Route Table](/images/5/5.png?featherlight=false&width=90pc)

6. Repeat adding a peering connection for route table **HG VPC Public Routes**.

![Configure Route Table](/images/5/6.png?featherlight=false&width=90pc)

7. Under the **Destination** column, enter **172.31.0.0/16**. Under the **Target** column, select the **VPC Peering** that we created.
 

![Configure Route Table](/images/5/7.png?featherlight=false&width=90pc)

8. Complete initialization.

![Configure Route Table](/images/5/8.png?featherlight=false&width=90pc)

9. From **EC2 - My VPC**, try pinging **private IP** of **EC2 - HG VPC**. Now we have succeeded.

![Configure Route Table](/images/5/9.png?featherlight=false&width=90pc)

10. However, when you try to ping **public DNS of EC2 - HG VPC**, you will fail because we have updated the Network ACL for the HG VPC subnets to prevent pings from the Internet. In the next section, you will click Cross-Peer DNS to fix this problem.

![Configure Route Table](/images/5/10.png?featherlight=false&width=90pc)

11. At this point, we have completed the proposed lab architecture:

![Configure Route Table](/images/5/11.png?featherlight=false&width=90pc)