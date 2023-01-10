---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### Overview
By default, VPCs inside AWS Cloud are separate and cannot communicate directly with each other. In this exercise, you will proceed to establish a VPC Peering connection between two VPCs so that the resources inside those two VPCs can communicate directly with each other. As a result, the communication between the two VPCs does not need to go through the public Internet anymore, contributing to increasing the security of the VPC.

You will create the following architecture for the exercise:

![VPC Peering](/images/1-Intro/0002.png?featherlight=false&width=60pc)


#### VPC Peering Connection

A **VPC Peering** connection is a network connection between two VPCs that allows you to route traffic between them using IPv4 or IPv6 private addresses. Instances in either VPC can communicate with each other as if they were on the same network.

![VPC Peering](/images/1-Intro/0004.png?featherlight=false&width=10pc)

#### Network Access Control List (Network ACL)

You've done a lot of practice with **Security Group** - a kind of stateful firewall at resource-level. In this article, you will use **Network ACL** - a type of stateless firewall at the subnet-level. Specifically, Network ACLs can only be assigned to the subnet, but not to each Instance within the subnet.

#### Cross-Peering DNS

**Cross-Peering DNS** is a feature of VPC Peering that allows resources within one VPC to resolve the DNS of another VPC.

{{% notice note %}}
Convention: VPC default = VPC 1; HG VPC = VPC 2.
{{% /notice %}}