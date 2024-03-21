---
title : "Truy cập vào user và đổi sang role cho workshop"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Truy cập vào user
1. Ở góc trên bên phải tài khoản hiện tai, Chọn nút **Sign Out**.
![switch](/images/2.prerequisite/015-switch.png)
2. Nhập những thông tin đã lưu của user workshop để đăng nhập vào.
![switch](/images/2.prerequisite/016-switch.png)
3. Sau khi login vào được, tài khoản đấy chưa làm được workshop, ta phải switch Role.
#### Đổi sang role cho workshop

1. Ở AWS management console:
  + Chọn thông tin user ở góc trên bên phải màn hình.
  + Chọn nút **Switch role**.
![switch](/images/2.prerequisite/017-switch.png)
2. Nhập những thông tin cần thiết vào:
  + Account: Nhập **Account ID**
  + Role: Nhập tên Role trong account đó. Ví dụ: workshop1-role.
  + Lưu ý: kiểm tra kỹ tên role chính xác, sai thì sẽ không switch role được.
  + Display Name sẽ tự động có.
  + Chọn màu phân biệt Role.
  + Bấm nút **Switch Role**.
![switch](/images/2.prerequisite/018-switch.png)
3. Sau khi Switch Role thành công thì ta sẽ thấy có màu của Role trên thông tin user đó và thử truy cập vào những dịch vụ được quyền vào.
![switch](/images/2.prerequisite/019-switch.png)
**Chúng ta đã hoàn thành xong thiết lập IAM để làm workshop này. Chúng ta sẽ bắt đầu với việc tạo S3 bucket.**