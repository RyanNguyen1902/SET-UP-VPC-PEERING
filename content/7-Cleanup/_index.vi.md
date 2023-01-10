---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

#### Dọn dẹp tài nguyên


Rất tuyệt vời!!! Chúc mừng các bạn đã vượt qua bài lab này. Hãy cùng dọn dẹp tài nguyên để tránh phát sinh chi phí cho tài khoản AWS của bạn nhé.

#### Xóa EC2 instnace

- Truy cập **EC2 Management Console**
- Trên thanh điều hướng bên trái, chọn **Intances**
- Chọn tất cả **EC2 Instance** liên quan tới bài lab.
- Click **Actions**.
- Click **Manage Instance State**.
![Clean](/images/7-clean/1.png?featherlight=false&width=90pc)

- Chọn **Terminate**.
- Click **Change State**

![Clean](/images/7-clean/2.png?featherlight=false&width=90pc)

#### Xóa VPC Peering Connection

- Truy cập **VPC Management Console**
- Trên thanh điều hướng bên trái, chọn **Peering Connections**
- Tick vào **VPC Peering Conenction** liên quan tới bài lab.
- Click **Actions**.
- Chọn **Delete VPC Peering Conenction**

![Clean](/images/7-clean/3.png?featherlight=false&width=90pc)

- Trong prompt, tick vào **Delete related route table entries**.
- Chọn **Yes, Delete**.

![Clean](/images/7-clean/4.png?featherlight=false&width=90pc)

#### Xóa Security Group

- Truy cập **EC2 Management Console**
- Trên thanh điều hướng bên trái, chọn **Security Groups**
- Chọn tất cả **Security Groups** liên quan tới bài lab.
- Click **Actions**.
- Click **Delete security groups**
- Click **Delete**

![Clean](/images/7-clean/5.png?featherlight=false&width=90pc)

#### Xóa CloudFormation Stack

- Truy cập vào **CloudFormation Management Console**
- Ở thanh bên trái, chọn **Stacks**.
- Lần lượt tick các vào **CloudFormation Stack** liên quan tới bài lab và chọn **Delete**.
- Trong prompt, chọn **Delete stack**.
- Đọi vài phút cho tới khi **CloudFormation** xóa bỏ hết tài nguyên.

![Clean](/images/7-clean/6.png?featherlight=false&width=90pc)