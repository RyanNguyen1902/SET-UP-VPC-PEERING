---
title : "Tạo kết nối Peering"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

#### Tạo kết nối Peering

Ở phần nảy, bạn sẽ tạo kết nối **VPC Peering** (**VPC Peering Connection**) giữa **My VPC và HG VPC**.

1. Đăng nhập vào **AWS Management Console**

   - Tìm **VPC**
   - Chọn **VPC**

![Create VPC Peering](/images/4/1.png?featherlight=false&width=90pc)

2. Ở **VPC Management Console***, điều hướng đến **Peering Connections**. Sau đó, nhấn chọn **Create Peering Connection.**

![Create VPC Peering](/images/4/2.PNG?featherlight=false&width=90pc)

3. Ở trang **Create Peering Connection**, nhập các thông số như sau rồi chọn **Create Peering Connection**:
   - **Peering connection name tag**: lab-vpc-peer
   - **VPC (Requester)**: chọn My VPC

![Create VPC Peering](/images/4/3.png?featherlight=false&width=90pc)

4. Đối với **Select another VPC to peer with**

   - **Account**: chọn **My account** vì 2 VPC trong **peering connection** nằm trong cùng một **account**
   - **Region**: chọn **This region (ap-southeast-1)** vì 2 VPC trong peering connection ở cùng một region.
   - **VPC (Accepter)**: HG VPC

![Create VPC Peering](/images/4/4.png?featherlight=false&width=90pc)

5. Hoàn thành **Create Peering Connection**

![Create VPC Peering](/images/4/5.png?featherlight=false&width=90pc)

6. Về trang thông tin của **Peering Connections**, tick **VPC Peering** vừa tạo sau đó nhấn **Actions** và **Accept Request**.

![Create VPC Peering](/images/4/6.png?featherlight=false&width=90pc)
![Create VPC Peering](/images/4/7.png?featherlight=false&width=90pc)

7. Chọn **Accept request**

![Create VPC Peering](/images/4/8.png?featherlight=false&width=90pc)

8. Thiết lập thành công.

![Create VPC Peering](/images/4/9.png?featherlight=false&width=90pc)

9. Từ **EC2 - My VPC**, hãy thử ping **private IP** của **EC2 - HG VPC**. Ping vẫn thất bại bởi vì chúng ta chưa cấu hình VPC router để định tuyến traffic giữa 2 VPC.

![Create VPC Peering](/images/4/10.png?featherlight=false&width=90pc)






