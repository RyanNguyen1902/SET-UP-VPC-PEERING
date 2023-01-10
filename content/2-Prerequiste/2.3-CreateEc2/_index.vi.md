---
title : "Tạo EC2 instance"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

#### Tạo EC2 instance

Ở bước này, bạn sẽ tạo hai máy ảo ở hai **Public Subnet 2** của hai **VPC**. Bài thực hành này sẽ giả định rằng bạn đã quen thuộc với quy trình khởi tạo EC2, nên những hướng dẫn dưới đây sẽ rất ngắn gọn. Nếu bạn vẫn chưa làm quen với quy trình khởi tạo EC2, hãy tham khảo bài lab **[KHỞI TẠO MÁY ẢO EC2](https://000004.awsstudygroup.com/vi/)**.

1. Truy cập vào EC2 Management Console bằng cách gõ EC2 vào thanh tìm kiếm.

![Create EC2 Instance](/images/2.3/27.png?featherlight=false&width=90pc)

2. Trong giao diện **EC2**

    - Chọn **Instances**
    - Chọn **Launch instances**

![Create EC2 Instance](/images/2.3/28.png?featherlight=false&width=90pc)

3. Thực hiện cấu hình **EC2**

   - **Name**, nhập **```EC2 - My VPC```**
   - Choose AMI: **Amazon Linux 2 AMI (HVM), SSD Volume Type**

![Create EC2 Instance](/images/2.3/29.png?featherlight=false&width=90pc)

4. Choose **Instance type**: t2.micro

    - Chọn **Create new key pair**


![Create EC2 Instance](/images/2.3/30.png?featherlight=false&width=90pc)

5. Trong giao diện **Create key pair**

    - **Key pair name**, nhập **```vpcpeering-key```**
    - **Key pair type**, chọn **RSA**
    - **Private key file format**, chọn **.pem**
    - Chọn **Create key pair**

![Create EC2 Instance](/images/2.3/31.png?featherlight=false&width=90pc)

6. Thực hiện cấu hình **Network**
   - **Network**: My VPC
   - **Subnet**: My VPC Public Subnet (AZ2)
   - **Auto-assign Public IP**: Enable
   - **Security group**, chọn **My VPC SG**  

![Create EC2 Instance](/images/2.3/32.png?featherlight=false&width=90pc)
![Create EC2 Instance](/images/2.3/33.png?featherlight=false&width=90pc)

- Sau đó chọn **Launch instance**
- Chọn **View all instance** để xem thông tin **instance**

![Create EC2 Instance](/images/2.3/34.png?featherlight=false&width=90pc)

7. Xem thông tin chi tiết **instance** vừa tạo.

![Create EC2 Instance](/images/2.3/35.png?featherlight=false&width=90pc)

8. Tiếp tục khởi tạo thêm **instance** nữa bằng cách chọn **Launch instances**.

![Create EC2 Instance](/images/2.3/36.png?featherlight=false&width=90pc)

9. Thực hiện cấu hình **instance**


   - **Name**, nhập **```EC2 - HG VPC```**

   - Choose AMI: **Amazon Linux 2 AMI (HVM), SSD Volume Type**

![Create EC2 Instance](/images/2.3/37.png?featherlight=false&width=90pc)

10. Choose **Instance type: t2.micro**


    - Chọn **Key pair** đã tạo.


![Create EC2 Instance](/images/2.3/38.png?featherlight=false&width=90pc)

11. Thực hiện cấu hình **Network**

    - **VPC**: HG VPC
    - **Subnet**: HG VPC Public Subnet (AZ2)
    - **Auto-assign Public IP**: Enable
    - **Security group**, chọn **HG VPC SG**
    - Chọn **Launch instance**

![Create EC2 Instance](/images/2.3/39.png?featherlight=false&width=90pc)

12. Tạo instance thành công, chọn **View all instance**

![Create EC2 Instance](/images/2.3/40.png?featherlight=false&width=90pc)

13. Xem thông tin chi tiết instance vừa tạo.

![Create EC2 Instance](/images/2.3/41.png?featherlight=false&width=90pc)

14. Bây giờ, bạn hãy thử kết nối SSH tới EC2 - My VPC và ping địa chỉ IP Public của EC2 - HG VPC. (với lệnh ```ping <IPv4 Public của EC2> -c5```)

Để kết nối SSH tới EC2 ta có cách. Kết nối Amazon EC2 Linux 2 bằng **MobaXterm** và kết nối Amazon EC2 Linux 2 bằng **PuTTY**. Ở đây mình kết nối Amazon EC2 Linux 2 bằng PuTTY.

Bạn có thể xem lại cách ở nối SSH tới EC2 truy cập ở Lab [**Giới thiệu về Amazon EC2 mục 4.2**](https://000004.awsstudygroup.com/vi/4-launchlinuxinstance/4.2-connectlinuxinstance/).

![Create EC2 Instance](/images/2.3/42.png?featherlight=false&width=90pc)

Bạn sẽ thấy ping thành công do hai instance đang giao tiếp với nhau qua Public Internet.

15. Giữ nguyên kết nối SSH tới **EC2 - My VPC**, giờ bạn hãy thử ping địa chỉ **IP Private** của **EC2 - HG VPC**. Bạn sẽ thấy ping không thành công do hai VPC là tách biệt và chưa có kết nối với nhau.

![Create EC2 Instance](/images/2.3/43.png?featherlight=false&width=90pc)