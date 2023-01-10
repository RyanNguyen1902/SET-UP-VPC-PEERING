---
title : "Kích hoạt Cross-Peer DNS"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---

#### Kích hoạt Cross-Peer DNS

Ở phần này, bạn sẽ kích hoạt tính năng **Cross-peering DNS** để cho phép **EC2 - My VPC** truy vấn **public DNS của EC2 - HG VPC** và trả về địa chỉ **IP private** của **VPC EC2- HG VPC** và kết nối khi đó sẽ đi qua mạng nội bộ của AWS.

{{% notice tip %}}
Nếu tính năng này không được kích hoạt thì kết nối giữa các **EC2 instance của EC2** - My VPC khi truy vấn public DNS của EC2 - HC VPC sẽ trả về địa chỉ IP public và kết nối lúc đó sẽ đi qua đường internet.
{{% /notice %}}

1. Quay trở lại **VPC Management Console**

![Cross-Peer DNS](/images/6/1.png?featherlight=false&width=90pc)

2. Chọn **Peering Connections** ở thanh bên trái. 

   - Sau đó, tick vào **VPC peering connection** giữa 2 VPC chúng ta đã tạo.
   - Chọn **Actions**
   - Chọn **Edit DNS settings**

![Cross-Peer DNS](/images/6/2.png?featherlight=false&width=90pc)

3. Trong trang **Edit DNS Settings**, tick vào hai box bên cạnh **Requester DNS resolution** và **Accepter DNS resolution**.

![Cross-Peer DNS](/images/6/3.png?featherlight=false&width=90pc)

4. Nhấn **Save** sau đó **Close**. Việc này sẽ cần vài phút để thực thi.

![Cross-Peer DNS](/images/6/4.png?featherlight=false&width=90pc)

5. Từ **EC2 - My VPC**, hãy thử ping **Public DNS của EC2 - HG VPC**, chúng ta sẽ ping thành công.

![Cross-Peer DNS](/images/6/5.png?featherlight=false&width=90pc)


