---
title : "Tạo S3 buckets cho batch translation"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.2.1 </b> "
---

### Tạo S3 bucket cho input
1. Trên console, vào thanh tìm kiếm, nhập vào **S3** để vào Amazon S3:
![batchS3](/images/2.prerequisite/020-batch.png)
2. Trong S3, chọn nút **Create bucket** để tạo bucket mới:
![batchS3](/images/2.prerequisite/021-batch.png)
3. Trong Create Bucket:
  + Chọn AWS Region: **Singapore (ap-southeast-1)**.
  + Nhập bucket name: ```translate-job-batch-input-<your_id>```. Ví dụ: translate-job-batch-input-150903.
{{% notice tip %}}
Chọn id của riêng bạn để không trùng với tên của các buckets khác trên Amazon S3.
{{% /notice %}}
![batchS3](/images/2.prerequisite/022-batch.png)
4. Các thông số khác để mặc định, chọn nút **Create Bucket**.
![batchS3](/images/2.prerequisite/023-batch.png)
5. Sau khi bucket tạo thành công, truy cập vào bucket.
  + Sau đó, chọn nút **Create folder**.
![batchS3](/images/2.prerequisite/024-batch.png)
6. Trong Create folder:
  + Nhập folder name: ```raw```.
  + Sau đó, chọn nút **Create folder**.
![batchS3](/images/2.prerequisite/025-batch.png)

### Tạo S3 bucket cho output
1. Trong S3, chọn nút **Create bucket** để tạo bucket mới:
![batchS3](/images/2.prerequisite/026-batch.png)
2. Trong Create Bucket:
  + Chọn AWS Region: **Singapore (ap-southeast-1)**.
  + Nhập bucket name: ```translate-job-batch-output-<your_id>```. Ví dụ: translate-job-batch-output-150903.
{{% notice tip %}}
Chọn id của riêng bạn để không trùng với tên của các buckets khác trên Amazon S3.
{{% /notice %}}
![batchS3](/images/2.prerequisite/027-batch.png)
3. Các thông số khác để mặc định, chọn nút **Create Bucket**.
![batchS3](/images/2.prerequisite/028-batch.png)
4. Sau khi bucket tạo thành công, truy cập vào bucket.
  + Sau đó, chọn nút **Create folder**.
![batchS3](/images/2.prerequisite/029-batch.png)
5. Trong Create folder:
  + Nhập folder name: ```output```.
  + Sau đó, chọn nút **Create folder**.
![batchS3](/images/2.prerequisite/030-batch.png)

**Bạn đã hoàn thành xong việc tạo 2 buckets cho batch translation**.