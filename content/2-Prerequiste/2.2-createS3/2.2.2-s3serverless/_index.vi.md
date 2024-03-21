---
title : "Tạo S3 buckets cho serverless translation"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2.2 </b> "
---

### Tạo s3 buckets cho serverless translation

1. Trong S3, chọn nút **Create bucket** để tạo bucket mới:
![s3serverless](/images/2.prerequisite/044-serverless.png)
2. Trong Create Bucket:
  + Chọn AWS Region: **Singapore (ap-southeast-1)**.
  + Nhập bucket name: ```batching-bucket-<your_id>```. Ví dụ: batching-bucket-150903.
{{% notice tip %}}
Chọn id của riêng bạn để không trùng với tên của các buckets khác trên Amazon S3.
{{% /notice %}}
![s3serverless](/images/2.prerequisite/045-serverless.png)
3. Các thông số khác để mặc định, chọn nút **Create Bucket**.
![s3serverless](/images/2.prerequisite/046-serverless.png)
4. Làm tương tự như 3 bước trên để tạo thành công 4 buckets như sau:
  + ```batching-bucket-<your_id>```
  + ```batched-bucket-<your_id>```
  + ```translated-bucket-<your_id>```
  + ```final-translated-bucket-<your_id>```
![s3serverless](/images/2.prerequisite/047-serverless.png)

**Hooray! bạn đã hoàn thành xong việc tạo các S3 buckets, tiếp theo chuẩn bị các lambda functions nào.**

