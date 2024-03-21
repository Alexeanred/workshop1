---
title : "Dọn dẹp tài nguyên lab"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

### S3
#### **Xóa các buckets đã tạo**
Ta cần xóa 4 buckets: **batching-bucket, batched-bucket, translated-bucket, final-translated-bucket**.

Làm theo 4 bước sau để xóa 1 bucket. Làm tương tự cho 3 buckets còn lại. 
1. Vào 1 bucket đã tạo:
  + Xóa các objects (files) trước.
  + Chọn tất cả các files.
  + Chọn nút **Delete**.
![clean](/images/5.fwd/001-cleanup.png)
2. Nhập vào **permanently delete**
  + Chọn nút **Delete objects**.
![clean](/images/5.fwd/002-cleanup.png)
3. Thoát ra ngoài giao diện S3:
  + Chọn bucket muốn xóa.
  + Chọn nút **Delete**
![clean](/images/5.fwd/003-cleanup.png)
4. Nhập tên bucket muốn xóa vào để xác nhận.
  + Chọn **Delete bucket**.
![clean](/images/5.fwd/004-cleanup.png)
### Lambda
Ta cần xóa 3 functions: **batchingFunction, combineFunction, translationFunction**.

Làm theo 2 bước sau để xóa 1 function. Làm tương tự cho 2 functions còn lại. 
1. Chọn 1 bucket cần xóa.
  + Vào **Actions**.
  + Chọn **Delete**
![clean](/images/5.fwd/005-cleanup.png)

2. Nhập ```delete```.
  + Chọn nút **Delete**.
![clean](/images/5.fwd/011-cleanup.png)
### Translate
Trong **Batch translation** thì ta không xóa được job đã hoàn thành.

Nó chỉ có 3 nút **Copy** để sao chép job hiện tại, **Stop** để dừng 1 job đang chạy, **Create job** để tạo job mới.
![clean](/images/5.fwd/006-cleanup.png)

### Cloudwatch
1. Truy cập vào **Cloudwatch**:
  + Chọn **Log groups**.
  + Chọn log của 1 hàm ta đã tạo.
![clean](/images/5.fwd/007-cleanup.png)
2. Trong mục **log streams**:
  + Chọn hết các logs.
  + Chọn nút **Delete**.
![clean](/images/5.fwd/008-cleanup.png)

### IAM
#### Xóa user ta đã tạo:
  + Chọn user: **workshop-1-user**.
  + Chọn nút **Delete**.
  + Nhập tên user lại để xác nhận.
  + Chọn nút **Delete user**.
![clean](/images/5.fwd/009-cleanup.png)
#### Xóa role ta đã tạo:
  + Chọn role: **workshop1-role**.
  + Chọn nút **Delete**.
  + Nhập tên role lại để xác nhận.
  + Chọn nút **Delete**.
  
Ngoài ra còn những role khác ta đã tạo, bạn có thể làm tương tự để xóa.
![clean](/images/5.fwd/010-cleanup.png)