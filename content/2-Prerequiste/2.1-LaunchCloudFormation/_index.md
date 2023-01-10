---
title : "Initialize CloudFormation Template"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Initialize CloudFormatuon Templates

This step will detail how to create **My VPC** with **CloudFormation Template**. You can repeat this step to create more HG VPCs. A stack can take up to 5 minutes to complete initialization.

- Method 1: First of all, we download **[CloudFormation Template](https://docs.aws.amazon.com/codebuild/latest/userguide/cloudformation-vpc-template.html)** to the computer.

- Method 2: You can download [Template](https://github.com/AWS-First-Cloud-Journey/AWS-CloudFormation-Template/archive/refs/heads/master.zip)


1. Login to **AWS Management Console**

   - Find **CloudFormation**
   - Select **CloudFormation**

![Launch CloudFormation](/images/2.1/1.png?featherlight=false&width=90pc)

{{%notice note%}}
In this workshop, we will use the Singapore region (ap-southeast-1). If you want to use another Region, be sure to move the Region back to the Region you want to use when creating workshop-related resources.
{{%/notice%}}

![Launch CloudFormation](/images/2.1/2.png?featherlight=false&width=90pc)

2. In the **CloudFormation** interface, select **Stack**

![Launch CloudFormation](/images/2.1/3.png?featherlight=false&width=90pc)

3. In the **Stack** interface, select **Create stack**

![Launch CloudFormation](/images/2.1/4.png?featherlight=false&width=90pc)

4. In the **Create stack** page select the following parameters and select **Next**:
   - **Prerequisite - Prepare template**:
     - **Prerequisite template**: Template is ready
   - **Specify template**:
     - **Template source***: Upload a template file
     - Select **Choose file** and then select the **VPCTempalte.yaml** file that has just been download.
   - Select **Next**

![Launch CloudFormation](/images/2.1/5.png?featherlight=false&width=90pc)

5. In the Specify stack details page, you will enter the required parameters in **VPCTempalte.yaml** as follows:
   - **Stack name**:
     - **Stack name**: ```My-VPC-Stack```
   - **Parameters**:
     - **EnvironmentName**: ```My VPC```
     - **PrivateSubnet1CIDR**: ```172.31.3.0/24```
     - **PrivateSubnet2CIDR**: ```172.31.4.0/24```
     - **PublicSubnet1CIDR**: ```172.31.1.0/24```
     - **PublicSubnet2CIDR**: ```172.31.2.0/24```
     - **VpcCIDR**: ```172.31.0.0/16```
   - Check and select **Next**

![Launch CloudFormation](/images/2.1/6.png?featherlight=false&width=90pc)

6. On the **Configure stack options** page, select **Next**

![Launch CloudFormation](/images/2.1/7.png?featherlight=false&width=90pc)

7. On the **Review** page, check and select **Submit** at the bottom of the page.

![Launch CloudFormation](/images/2.1/8.png?featherlight=false&width=90pc)

8. Wait 10 minutes, **Stack** created successfully.

![Launch CloudFormation](/images/2.1/9.png?featherlight=false&width=90pc)

9. View **Output** of the newly created Stack.

![Launch CloudFormation](/images/2.1/10.png?featherlight=false&width=90pc)

10. Repeat steps to create **HG VPC**

- In the left sidebar, select **Stacks**. Then select **Create stack** and select **With new resources (standard)**.


![Launch CloudFormation](/images/2.1/11.png?featherlight=false&width=90pc)

11. In the Create stack page select the following parameters and select Next:
    - **Prerequisite - Prepare template**:
    - **Prerequisite template**: Template is ready
    - **Specify template**:
    - **Template source**: Upload a template file
    - Select **Choose file** and then select the **VPCTempalte.yaml** file that has just been created.

![Launch CloudFormation](/images/2.1/12.png?featherlight=false&width=90pc)

12. Stack name:

    - **Stack name**: ```HG-VPC-Stack```
    - **Parameters**:
      - **EnvironmentName**: ```HG VPC```
      - **PrivateSubnet1CIDR**: ```10.10.3.0/24```
      - **PrivateSubnet2CIDR**: ```10.10.4.0/24```
      - **PublicSubnet1CIDR**: ```10.10.1.0/24```
      - **PublicSubnet2CIDR**: ```10.10.2.0/24```
      - **VpcCIDR**: ```10.10.0.0/16```


![Launch CloudFormation](/images/2.1/13.png?featherlight=false&width=90pc)

13. On the Configure stack options page, select Next


![Launch CloudFormation](/images/2.1/14.png?featherlight=false&width=90pc)

14. On the Review page, check and select **Submit** at the bottom of the page. Wait 10 minutes after completing the stack creation.

![Launch CloudFormation](/images/2.1/15.png?featherlight=false&width=90pc)

15. View **Output** stack just created.

![Launch CloudFormation](/images/2.1/16.png?featherlight=false&width=90pc)