---
title : "Thêm trigger vào batching function"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1.1 </b> "
---
1. Truy cập vào batching function ở Lambda đã khởi tạo ở bước 2:
    + Chọn **Add trigger**.
![batchingfunc](/images/4.s3/001-batching.png)
2. Trong thanh tìm kiếm:
    + Nhập **S3**.
![batchingfunc](/images/4.s3/002-batching.png)
3. Trong **Trigger configuration**:
    + Bucket: **batching-bucket-<your_id>**.
    + Event types: để mặc định: **All object create events**.
    + Tick vào: **I acknowledge that ...**.
    + Chọn nút **Add**.
![batchingfunc](/images/4.s3/003-batching.png)

**Bạn đã thành công thêm trigger vào function.**