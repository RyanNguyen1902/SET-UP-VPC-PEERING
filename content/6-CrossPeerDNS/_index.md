---
title : "Enable Cross-Peer DNS"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Enable Cross-Peer DNS

In this section, you will enable **Cross-peering DNS** to allow **EC2 - My VPC** to query EC2 - HG VPC**'s public DNS and return the **IP address private** of the **VPC EC2- HG VPC** and the connection will then go through the AWS intranet.

{{% notice tip %}}
If this feature is not enabled, the connection between **EC2 instances of EC2** - My VPC when querying EC2's public DNS - HC VPC will return the public IP address and the connection will then go through the Internet.
{{% /notice %}}

1. Return to **VPC Management Console**

![Cross-Peer DNS](/images/6/1.png?featherlight=false&width=90pc)

2. Select **Peering Connections** in the left sidebar.

   - Then, tick **VPC peering connection** between the 2 VPCs we have created.
   - Select **Actions**
   - Select **Edit DNS settings**


![Cross-Peer DNS](/images/6/2.png?featherlight=false&width=90pc)

3. In the **Edit DNS Settings** page, check the two boxes next to **Requester DNS resolution** and **Accepter DNS resolution**.


![Cross-Peer DNS](/images/6/3.png?featherlight=false&width=90pc)

4. Click **Save** then **Close**. This will take a few minutes to execute.

![Cross-Peer DNS](/images/6/4.png?featherlight=false&width=90pc)

5. From **EC2 - My VPC**, try to ping **Public DNS of EC2 - HG VPC**, and we will ping successfully.

![Cross-Peer DNS](/images/6/5.png?featherlight=false&width=90pc)