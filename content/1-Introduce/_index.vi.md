---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Tổng quan
Theo mặc định, các VPC bên trong AWS Cloud là tách biệt và không thể giao tiếp trực tiếp với nhau. Ở bài thực hành này, bạn sẽ tiến hành thiết lập kết nối VPC Peering giữa hai VPC để các tài nguyên bên trong hai VPC đó có thể liên lạc trực tiếp với nhau. Nhờ vậy, các giao tiếp giữa hai VPC không cần phải thông qua Internet công cộng nữa, góp phần gia tăng tính bảo mật cho VPC.

Bạn sẽ tạo ra kiến trúc cho bài thực hành như sau:

![VPC Peering](/images/1-Intro/0002.png?featherlight=false&width=60pc)


#### VPC Peering Connection

Kết nối **VPC Peering** là một kết nối mạng giữa 2 VPC cho phép bạn định tuyến traffic giữa chúng sử dụng địa chỉ private IPv4 hoặc IPv6. Những instance ở trong 1 trong 2 VPC có thể giao tiếp với nhau như chúng đang nằm cùng 1 mạng.

![VPC Peering](/images/1-Intro/0004.png?featherlight=false&width=10pc)

#### Network Access Control List (Network ACL)

Bạn đã thực hành nhiều với **Security Group** - một dạng stateful firewall ở quy mô tài nguyên (resource-level). Trong bài này, bạn sẽ sử dụng **Network ACL** - một dạng statelesss firewall ở quy mô subnet (subnet-level). Cụ thể, Network ACL chỉ có thể được gán vào subnet chứ không thể gán vào từng Instance bên trong subnet.

#### Cross-Peering DNS

**Cross-Peering DNS** là một tính năng của VPC Peering cho phép các tài nguyên bên trong một VPC phân giải DNS của một tài nguyên khác VPC.

{{% notice note %}} 
Quy ước: VPC default = VPC 1; HG VPC = VPC 2.
{{% /notice %}}