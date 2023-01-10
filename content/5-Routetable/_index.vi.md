---
title : "Cấu hình Route tables"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

#### Cấu hình Route tables


1. Đăng nhập **AWS Management Console**

   - Tìm **VPC**
   - Chọn **VPC**

![Configure Route Table](/images/5/1.png?featherlight=false&width=90pc)

2. Truy cập vào **VPC Management Console**, chọn **Route tables** ở thanh bên trái.

![Configure Route Table](/images/5/2.png?featherlight=false&width=90pc)

3. Tick vào route table **My VPC Pubilc Routes**, chọn tab **Routes** ở màn hình bên dưới và chọn **Edit routes**

![Configure Route Table](/images/5/3.png?featherlight=false&width=90pc)

4. Chọn Add route. Dưới cột **Destination**, nhập **10.10.0.0/16**. Dưới cột **Target**, chọn **Peering connection** mà ta đã tạo.

![Configure Route Table](/images/5/4.png?featherlight=false&width=90pc)

5. Nhấn **Save changes**. Như vậy, bạn đã điều hướng các query cho block **10.10.0.0/16** (CIDR của HG VPC) đi tới **Peering connection** mà bạn đã tạo

![Configure Route Table](/images/5/5.png?featherlight=false&width=90pc)

6. Lặp lại thêm peering connection cho route table **HG VPC Public Routes**.

![Configure Route Table](/images/5/6.png?featherlight=false&width=90pc)

7. Dưới cột **Destination**, nhập **172.31.0.0/16**. Dưới cột **Target**, chọn **VPC Peering** mà ta đã tạo.
 

![Configure Route Table](/images/5/7.png?featherlight=false&width=90pc)

8. Hoàn thành khởi tạo.

![Configure Route Table](/images/5/8.png?featherlight=false&width=90pc)

9. Từ **EC2 - My VPC**, hãy thử ping **private IP** của **EC2 - HG VPC**. Bây giờ chúng ta đã thành công.

![Configure Route Table](/images/5/9.png?featherlight=false&width=90pc)

10. Tuy nhiên, khi thử ping **public DNS của EC2 - HG VPC**, bạn sẽ thất bại vì chúng ta đã cập nhật Network ACL cho các subnet của HG VPC ngăn chặn hoạt động ping từ Internet. Ở phần tiếp theo, bạn sẽ kích Cross-Peer DNS để khắc phục sự cố này.

![Configure Route Table](/images/5/10.png?featherlight=false&width=90pc)

11. Tới đây, chúng ta đã hoàn thành kiến trúc bài lab đề ra:

![Configure Route Table](/images/5/11.png?featherlight=false&width=90pc)




