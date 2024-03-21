---
title : "Cấp quyền cho user assume role"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Cấp quyền cho user

1. Truy cập vào user **workshop-1-user** vừa tạo:
  + Chọn nút **Add permissions**.
  + Chọn **Create inline policy**.

![assume](/images/2.prerequisite/012-assume.png)

2. Ở Step 1:
  + Chọn mục **JSON**.
  + Copy và dán vào những dòng sau:
```
  {
    "Version": "2012-10-17",
    "Statement": {
        "Effect": "Allow",
        "Action": "sts:AssumeRole",
        "Resource": [
            "arn:aws:iam::<your_AWS_account_id>:role/workshop1-role",
        ]
    }
}
```
  + Chọn nút **Next**.
{{% notice note %}}
Thay **<your_AWS_account_id>** thành id của bạn. Ví dụ: arn:aws:iam::030444900838:role/workshop1-role.
{{% /notice %}}

![assume](/images/2.prerequisite/013-assume.png)

3. Ở Step 2:
  + Nhập Policy name: **AssumeRoleWorkshop1**.
  + Chọn nút **Create policy**.

![assume](/images/2.prerequisite/014-assume.png)

Bạn đã hoàn thành việc **cấp quyền cho user assume role**, bước cuối cùng là **đăng nhập vào user và đổi sang role cho workshop**. 
