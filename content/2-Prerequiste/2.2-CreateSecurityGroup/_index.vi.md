---
title : "Tạo Security Group"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

#### Tạo Security Group

Bước này sẽ hướng dẫn chi tiết cách tạo **My VPC SG** bằng **CloudFormation Template**. Bạn có thể lặp lại bước này để tạo thêm **HG VPC SG**.

Để xác định các rule **Inbound** cần có, bạn liệt kê ra các yêu cầu như sau:

Bạn có thể kết nối **SSH vào EC2 instance** với source là IP của bạn.
- Hai **EC2 instance** ở hai VPC có thể được ping thông qua giao thức ICMP - IPv4 với source là Anywhere.
- Hai **EC2 instance** ở hai VPC có thể ping nhau bằng giao thức **ICMP - IPv4** với source là CIDR của VPC còn lại.

1. Truy cập vào AWS Management Console. Lựa chọn Services ở thanh điều hướng và tìm kiếm dịch vụ **VPC**.


![Create Security Group](/images/2.2/17.png?featherlight=false&width=90pc)

2. Trong giao diện **VPC**

   - Ở thanh điều hướng bên trái, chọn **Security Groups**.
   - Ở trang **Security Groups**, chọn **Create Security Group**.

![Create Security Group](/images/2.2/18.png?featherlight=false&width=90pc)

3. Ở trang Create security group, thiết lập các thông số như sau:
   - Mục **Basic details**:
     - **Security group name**: Nhập vào tên security group (VD: MY VPC SG)
     - **Description**: Nhập vào diễn giải của security group.
     - **VPC**: Chọn My VPC

![Create Security Group](/images/2.2/19.png?featherlight=false&width=90pc)

4. Mục Inbound rules: Thêm các Inbound rule như đề cập ở trên. Chọn Add rule để thêm một rule.
   - **Type**: SSH | **Source**: My IP
   - **Type**: All ICMP - IPv4 | **Source**: Anywhere
   - **Type**: All ICMP - IPv4 | **Source**: Custom 10.10.0.0/16 (CIDR của HG VPC)

![Create Security Group](/images/2.2/20.png?featherlight=false&width=90pc)

5. Chọn **Create security group**.

![Create Security Group](/images/2.2/21.png?featherlight=false&width=90pc)

6. Tạo **Security Group** thành công.

![Create Security Group](/images/2.2/22.png?featherlight=false&width=90pc)

7. Lặp lại các bước để tạo **HG VPC SG** như sau:

   - Mục **Basic details**:
     - **Security group name**: Nhập vào tên security group (VD: HG VPC SG)
     - **Description**: Nhập vào diễn giải của security group.
     - **VPC**: Chọn HG VPC


![Create Security Group](/images/2.2/23.png?featherlight=false&width=90pc)

8. Mục **Inbound rules**: Thêm các Inbound rule như đề cập ở trên. Chọn Add rule để thêm một rule.
   - **Type**: SSH | Source: My IP
   - **Type**: All ICMP - IPv4 | Source: Anywhere
   - **Type**: All ICMP - IPv4 | Source: Custom 172.31.0.0/16 (CIDR của My VPC)


![Create Security Group](/images/2.2/24.png?featherlight=false&width=90pc)

9. Chọn **Create security group**.

![Create Security Group](/images/2.2/25.png?featherlight=false&width=90pc)

10. Tạo **Security group** thành công.

![Create Security Group](/images/2.2/26.png?featherlight=false&width=90pc)

