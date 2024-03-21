---
title : "Tạo IAM user và IAM role"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, ta sẽ tạo 1 user cho workshop và gán role chứa các policies cần thiết. Chúng ta thực hành theo best practices là least privilege.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![IAM](/images/IAM-architecture.png)

Bạn cũng có thể tham khảo bài lab này trên aws study group :
  - [Giới thiệu về IAM](https://000002.awsstudygroup.com/)


### Nội dung
  - [Tạo workshop user](2.1.1-createuser/)
  - [Tạo workshop role](2.1.2-createrole/)
  - [Cấp quyền user assume role](2.1.3-assumerole/)
  - [Truy cập user và đổi sang role cho workshop](2.1.4-switchrole/)

