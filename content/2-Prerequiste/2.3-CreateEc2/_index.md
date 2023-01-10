---
title : "Create EC2 instance"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

#### Create EC2 instance

In this step, you will create two virtual machines in two **Public Subnet 2** of two **VPC**. This exercise will assume that you are familiar with the EC2 initialization process, so the instructions below will be very brief. If you are still not familiar with the EC2 initialization process, refer to the lab **[Initialize EC2 VMs](https://000004.awsstudygroup.com/en/)**.

1. Access the EC2 Management Console by typing EC2 in the search bar.

![Create EC2 Instance](/images/2.3/27.png?featherlight=false&width=90pc)

2. In the **EC2** interface

    - Select **Instances**
    - Select **Launch instances**

![Create EC2 Instance](/images/2.3/28.png?featherlight=false&width=90pc)

3. Perform configuration **EC2**

   - **Name**, enter **```EC2 - My VPC```**
   - Choose AMI: **Amazon Linux 2 AMI (HVM), SSD Volume Type**

![Create EC2 Instance](/images/2.3/29.png?featherlight=false&width=90pc)

4. Choose **Instance type**: t2.micro

    - Select **Create new key pair**


![Create EC2 Instance](/images/2.3/30.png?featherlight=false&width=90pc)

5. In the **Create key pair** interface

    - **Key pair name**, enter **```vpcpeering-key```**
    - **Key pair type**, select **RSA**
    - **Private key file format**, select **.pem**
    - Select **Create key pair**

![Create EC2 Instance](/images/2.3/31.png?featherlight=false&width=90pc)

6. Configure **Network**
   - **Network**: My VPC
   - **Subnet**: My VPC Public Subnet (AZ2)
   - **Auto-assign Public IP**: Enable
   - **Security group**, select **My VPC SG**
![Create EC2 Instance](/images/2.3/32.png?featherlight=false&width=90pc)
![Create EC2 Instance](/images/2.3/33.png?featherlight=false&width=90pc)

   - Then select **Launch instance**
   - Select **View all instance** to view information **instance**

![Create EC2 Instance](/images/2.3/34.png?featherlight=false&width=90pc)

7. View details **instance** just created.

![Create EC2 Instance](/images/2.3/35.png?featherlight=false&width=90pc)

8. Continue to initialize more **instance** by selecting **Launch instances**.

![Create EC2 Instance](/images/2.3/36.png?featherlight=false&width=90pc)

9. Configure **instance**


   - **Name**, enter **```EC2 - HG VPC```**

   - Choose AMI: **Amazon Linux 2 AMI (HVM), SSD Volume Type**

![Create EC2 Instance](/images/2.3/37.png?featherlight=false&width=90pc)

10. Choose **Instance type: t2.micro**

    - Select **Key pair** created.

![Create EC2 Instance](/images/2.3/38.png?featherlight=false&width=90pc)

11. Perform configuration **Network**

    - **VPC**: HG VPC
    - **Subnet**: HG VPC Public Subnet (AZ2)
    - **Auto-assign Public IP**: Enable
    - **Security group**, select **HG VPC SG**
    - Select **Launch instance**

![Create EC2 Instance](/images/2.3/39.png?featherlight=false&width=90pc)

12. Successful instance creation, select **View all instance**

![Create EC2 Instance](/images/2.3/40.png?featherlight=false&width=90pc)

13. View the details of the newly created instance.

![Create EC2 Instance](/images/2.3/41.png?featherlight=false&width=90pc)

14. Now try SSH connection to EC2 - My VPC and ping EC2 - HG VPC's Public IP address. (with the command ```ping <EC2 Public IPv4> -c5```) 

To connect SSH to EC2 we have a way. Connect Amazon EC2 Linux 2 using **MobaXterm** and connect Amazon EC2 Linux 2 using **PuTTY**. Here I connect Amazon EC2 Linux 2 using PuTTY.

You can review how to connect SSH to EC2 access at Lab [**About Amazon EC2 section 4.2**](https://000004.awsstudygroup.com/en/4-launchlinuxinstance/4.2-connectlinuxinstance/) .

![Create EC2 Instance](/images/2.3/42.png?featherlight=false&width=90pc)

You will see a successful ping because the two instances are communicating with each other over the Public Internet.

15. Keep SSH connection to **EC2 - My VPC**, now try pinging **EC2 - HG VPC**'s **IP Private** address. You will see that the ping failed because the two VPCs are separate and not yet connected.

![Create EC2 Instance](/images/2.3/43.png?featherlight=false&width=90pc)