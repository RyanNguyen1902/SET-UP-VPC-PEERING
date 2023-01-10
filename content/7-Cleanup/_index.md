---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

#### Clean up resources


Great!!! Congratulations on passing this lab. Let's clean up resources to avoid incurring costs for your AWS account.

#### Delete EC2 instance

- Access **EC2 Management Console**
- On the left navigation bar, select **Intances**
- Select all **EC2 Instance** related to the lab.
- Click **Actions**.
- Click **Manage Instance State**.
- Select **Terminate**.
- Click **Change State**

#### Remove VPC Peering Connection

- Access **VPC Management Console**
- On the left navigation bar, select **Peering Connections**
- Tick on **VPC Peering Connection** related to the lab.
- Click **Actions**.
- Select **Delete VPC Peering Connection**
- In the prompt, tick **Delete related route table entries**.
- Select **Yes, Delete**.

#### Delete Security Group

- Access **EC2 Management Console**
- On the left navigation bar, select **Security Groups**
- Select all **Security Groups** related to the lab.
- Click **Actions**.
- Click **Delete security groups**
- Click **Delete**

#### Clear CloudFormation Stack

- Access to **CloudFormation Management Console**
- In the left sidebar, select **Stacks**.
- In turn, tick the **CloudFormation Stack** related to the lab and select **Delete**.
- In the prompt, select **Delete stack**.
- Wait a few minutes until **CloudFormation** clears all resources.