---
title : "Thêm trigger vào translate function"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.2.1 </b> "
---

1. Truy cập vào translate function ở Lambda đã khởi tạo ở bước 2:
    + Chọn **Add trigger**.
![translatefunc](/images/4.s3/001-translate.png)
2. Trong thanh tìm kiếm:
    + Nhập **S3**.
![translatefunc](/images/4.s3/002-translate.png)
3. Trong **Trigger configuration**:
    + Bucket: **batched-bucket-<your_id>**.
    + Event types: để mặc định: **All object create events**.
    + Tick vào: **I acknowledge that ...**.
    + Chọn nút **Add**.
![translatefunc](/images/4.s3/003-translate.png)

**Bạn đã thành công thêm trigger vào function**


