---
title : "Thêm trigger vào combine function"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.3.1 </b> "
---

1. Truy cập vào combine function ở Lambda đã khởi tạo ở bước 2:
    + Chọn **Add trigger**.
![combinefunc](/images/4.s3/001-combine.png)
2. Trong thanh tìm kiếm:
    + Nhập **S3**.
![combinefunc](/images/4.s3/002-combine.png)
3. Trong **Trigger configuration**:
    + Bucket: **translated-bucket-<your_id>**.
    + Event types: để mặc định: **All object create events**.
    + Tick vào: **I acknowledge that ...**.
    + Chọn nút **Add**.
![combinefunc](/images/4.s3/003-combine.png)

**Bạn đã thành công thêm trigger vào function.**
