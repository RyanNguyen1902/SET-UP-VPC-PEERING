---
title : "Khởi tạo CloudFormation Template"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

#### Khởi tạo CloudFormatuon Templates

Bước này sẽ hướng dẫn chi tiết cách tạo **My VPC** bằng **CloudFormation Template**. Bạn có thể lặp lại bước này để tạo thêm HG VPC. Một stack có thể cần tới 5 phút để hoàn tất khởi tạo.

- Cách 1: Trước hết chúng ta tải **[CloudFormation Template](https://docs.aws.amazon.com/codebuild/latest/userguide/cloudformation-vpc-template.html)** về máy.

- Cách 2: Bạn có thể tải [Template](https://github.com/AWS-First-Cloud-Journey/AWS-CloudFormation-Template/archive/refs/heads/master.zip)


1. Đăng nhập vào **AWS Management Console**

   - Tìm **CloudFormation**
   - Chọn **CloudFormation**

![Launch CloudFormation](/images/2.1/1.png?featherlight=false&width=90pc)

{{%notice tip%}}
Trong workshop này, chúng ta sẽ sử dụng Region Singapore ( ap-southeast-1 ). Nếu bạn muốn sử dụng Region khác , hãy đảm bảo chuyển Region về Region bạn muốn sử dụng khi tạo các tài nguyên liên quan tới workshop.
{{%/notice%}}

![Launch CloudFormation](/images/2.1/2.png?featherlight=false&width=90pc)

2. Trong giao diện **CloudFormation**, chọn **Stack**

![Launch CloudFormation](/images/2.1/3.png?featherlight=false&width=90pc)

3. Trong giao diện **Stack**, chọn **Create stack**

![Launch CloudFormation](/images/2.1/4.png?featherlight=false&width=90pc)

4. Trong trang **Create stack** chọn các thông số sau và chọn **Next**:
   - **Prerequisite - Prepare template**:
     - **Prerequisite template**: Template is ready
   - **Specify template**:
     - **Template source***: Upload a template file
     - Chọn **Choose file** rồi chọn tập tin **VPCTempalte.yaml** vừa được tải về trước đó .
   - Chọn **Next**

![Launch CloudFormation](/images/2.1/5.png?featherlight=false&width=90pc)

5. Trong trang Specify stack details, bạn sẽ nhập các thông số được yêu cầu trong **VPCTempalte.yaml** như sau:
   - **Stack name**:
     - **Stack name**: ```My-VPC-Stack```
   - **Parameters**:
     - **EnvironmentName**: ```My VPC```
     - **PrivateSubnet1CIDR**: ```172.31.3.0/24```
     - **PrivateSubnet2CIDR**: ```172.31.4.0/24```
     - **PublicSubnet1CIDR**: ```172.31.1.0/24```
     - **PublicSubnet2CIDR**: ```172.31.2.0/24```
     - **VpcCIDR**: ```172.31.0.0/16```
   - Kiểm tra và chọn **Next**

![Launch CloudFormation](/images/2.1/6.png?featherlight=false&width=90pc)

6. Tại trang **Configure stack options**, chọn **Next**

![Launch CloudFormation](/images/2.1/7.png?featherlight=false&width=90pc)

7. Tại trang **Review**, kiểm tra và chọn **Submit** ở cuối trang.

![Launch CloudFormation](/images/2.1/8.png?featherlight=false&width=90pc)

8. Đợi 10 phút sau, **Stack** tạo thành công.

![Launch CloudFormation](/images/2.1/9.png?featherlight=false&width=90pc)

9. Xem **Ouput** của Stack vừa tạo.

![Launch CloudFormation](/images/2.1/10.png?featherlight=false&width=90pc)

10. Thực hiện các bước lặp lại để tạo **HG VPC**

- Ở thanh bên trái, chọn **Stacks**. Sau đó, chọn **Create stack** và chọn **With new resources (standard)**.

![Launch CloudFormation](/images/2.1/11.png?featherlight=false&width=90pc)

11. Trong trang Create stack chọn các thông số sau và chọn Next:
    - **Prerequisite - Prepare template**:
    - **Prerequisite template**: Template is ready
    - **Specify template**:
    - **Template source**: Upload a template file
    - Chọn **Choose file** rồi chọn tập tin **VPCTempalte.yaml** vừa được tải về trước đó.

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

13. Tại trang Configure stack options, chọn **Next**

![Launch CloudFormation](/images/2.1/14.png?featherlight=false&width=90pc)

14. Tại trang Review, kiểm tra và chọn **Submit** ở cuối trang. Đợi 10 phút sau hoàn thành tạo stack.

![Launch CloudFormation](/images/2.1/15.png?featherlight=false&width=90pc)

15. Xem **Output** stack vừa tạo.

![Launch CloudFormation](/images/2.1/16.png?featherlight=false&width=90pc)


