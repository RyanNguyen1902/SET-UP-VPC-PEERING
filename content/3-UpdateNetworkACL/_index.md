---
title : "Update Network ACL"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Update Network ACL

1. Go to **AWS Management Console**

   - Find **VPC**
   - Select **VPC**

![Create EC2 Instance](/images/3/1.png?featherlight=false&width=90pc)

2. Go to **VPC Management Console** and select **Network ACLs** in the left sidebar.
   - Tick on **Network ACL** being assigned to the subnets of HG VPC.
   - Next, click the **Inbound Rules** tab at the bottom of the screen, and click **Edit inbound rules**.

![Create EC2 Instance](/images/3/2.png?featherlight=false&width=90pc)

3. We will change **Rule number 100**. Under Source change **0.0.0.0/0** to **172.31.0.0/16** and click Save changes.

![Create EC2 Instance](/images/3/3.png?featherlight=false&width=90pc)

4. Thus, you have reduced the range of IP addresses that can be connected to the subnets of **HG VPC**. Now, only IP addresses in block **172.31.0.0/16** (My VPC's CIDR) can connect to HG VPC subnets.

![Create EC2 Instance](/images/3/4.png?featherlight=false&width=90pc)

5. Back in the terminal, try pinging **EC2 - HG VPC**'s public IP address again. You will see a ping failure because the connection from the Internet to the HG VPC has been limited by the **Network ACL** that has just been updated.

![Create EC2 Instance](/images/3/5.png?featherlight=false&width=90pc)