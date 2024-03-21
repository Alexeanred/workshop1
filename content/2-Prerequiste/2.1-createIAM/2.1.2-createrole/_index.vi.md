---
title : "Tạo workshop role"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Tạo Role

1. Trong trang IAM:
  + Chọn mục **Roles**.
  + Chọn **Create role**.
![role](/images/2.prerequisite/007-role.png)

2. Trong Step 1:
  + Chọn **AWS account**.
  + Chọn **This account**.
  + Chọn nút **Next**.
![role](/images/2.prerequisite/008-role.png)

3. Trong Step 2:
  + **Copy các policy names** sau vào thanh tìm kiếm và tick vào chọn:
    + ```AmazonS3FullAccess```
    + ```AWSLambda_FullAccess```
    + ```CloudWatchFullAccess```
    + ```IAMFullAccess```
    + ```TranslateFullAccess```
  + Chọn nút **Next**.
![role](/images/2.prerequisite/009-role.png)

4. Trong step 3:
  + Nhập role name: ```workshop1-role```.
  + Review lại mục **Trust policy** xem có cho phép dùng role trên tài khoản này không.
![role](/images/2.prerequisite/010-role.png)

5. Xem lại các quyền mình đã cấp cho role thông qua các policy name.
  + Thêm tags nếu cần và chọn nút **Create role**.
![role](/images/2.prerequisite/011-role.png)
**Bạn đã hoàn thành xong việc tạo role cho workshop user.**
