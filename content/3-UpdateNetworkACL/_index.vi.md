---
title : "Cập nhật Network ACL"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

#### Cập nhật Network ACL

1. Truy cập vào **AWS Management Console**

   - Tìm **VPC**
   - Chọn **VPC**

![Create EC2 Instance](/images/3/1.png?featherlight=false&width=90pc)

2. Đi đến **VPC Management Console** và chọn **Network ACLs** ở thanh bên trái.
   - Tick vào **Network ACL** đang được gán với các subnet của HG VPC.
   - Tiếp theo, nhấn chọn tab **Inbound Rules** ở dưới màn hình, và nhấn **Edit inbound rules**.

![Create EC2 Instance](/images/3/2.png?featherlight=false&width=90pc)

3. Chúng ta sẽ thay đổi **Rule number 100**. Dưới Source đổi **0.0.0.0/0** thành **172.31.0.0/16** và nhấn Save changes.

![Create EC2 Instance](/images/3/3.png?featherlight=false&width=90pc)

4. Như vậy, bạn đã thu nhỏ khoảng địa chỉ IP có thể kết nối tới các subnet của **HG VPC**. Bây giờ, chỉ các địa chỉ IP trong block **172.31.0.0/16** (CIDR của My VPC) mới có thể kết nối tới các subnet của HG VPC.

![Create EC2 Instance](/images/3/4.png?featherlight=false&width=90pc)

5. Trở lại terminal, thử ping địa chỉ public Ip của **EC2 - HG VPC** lần nữa. Bạn sẽ thấy ping thất bại vì kết nối từ Internet tới HG VPC đã bị giới hạn bởi **Network ACL** vừa được cập nhật.

![Create EC2 Instance](/images/3/5.png?featherlight=false&width=90pc)