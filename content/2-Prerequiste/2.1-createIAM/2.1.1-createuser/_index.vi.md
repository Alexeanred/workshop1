---
title : "Tạo workshop user "
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1.1 </b> "
---


#### Tạo workshop IAM user
1. Truy cập vào console:
  + Vào thanh tìm kiếm.
  + Nhập **IAM**.

![user](/images/2.prerequisite/001-user.png)

2. Tại trang **IAM**.
  + Chọn mục **user**.
  + Chọn nút **Create user**.

![user](/images/2.prerequisite/002-user.png)

3. Trong Step 1:
  + Nhập user name: ```workshop-1-user```.
  + Chọn **Provide user access to the AWS Management Console**.
  + Chọn user type: **I want to create an IAM user**.
  + Chọn **custom password**: nhập password cho user đó.
  + Bỏ chọn **Users must create a new password at next sign-in**.
  + Chọn nút **Next**.
![user](/images/2.prerequisite/003-user.png)

4. Trong Step 2, chọn **Add user to group**.
  + Chọn nút **Next**.
![user](/images/2.prerequisite/004-user.png)

5. Trong Step 3, xem lại thông tin và chọn nút **Create user**.
![user](/images/2.prerequisite/005-user.png)
6. Trong Step 4, copy lại những thông tin cần thiết cho đăng nhập vào user.
![user](/images/2.prerequisite/006-user.png)
**Bạn đã tạo xong user cho workshop 1, tiếp theo là tạo workshop role.**