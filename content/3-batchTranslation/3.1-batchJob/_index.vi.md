---
title : "Tạo batch translation job"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

1. Ở console, trong thanh tìm kiếm, nhập ```Translate```.
![bathjob](/images/3.connect/001-batchTranslate.png)
2. Trong giao diện Translate:
    + Chọn **Batch translation**.
    + Chọn nút **Create job**.
![bathjob](/images/3.connect/002-batchTranslate.png)
3. Trong **Create Translate Job**:
    + Ở mục **Name**, nhập ```MyTranslateJob```.
    + Chọn source language: **English**.
    + Chọn target language: **Vietnamese**.
![bathjob](/images/3.connect/003-batchTranslate.png)
4. Ở mục Input data:
    + Chọn nút **Select folder** .
    + Truy cập vào đường dẫn thư mục trong input bucket: **s3://translate-job-batch-input-150903/raw/**.
    + Chọn dạng File format: **Plain text (.txt)**.
    + Truy cập vào đường dẫn thư mục trong output bucket: **s3://translate-job-batch-output-150903/output/**.
    + Dữ liệu của bạn đã được mã hóa mặc định.
![bathjob](/images/3.connect/005-batchTranslate.png)
5. Ta phải cấp quyền cho Translate truy cập vào S3 buckets:
    + Chọn tạo mới IAM role **Create an IAM role**.
    + Trong mục IAM role: Chọn **Input and output S3 buckets** nếu bạn muốn chỉ cho quyền Translate truy cập vào 2 buckets này.
    + Nếu muốn cho tất cả buckets thì chọn **Any S3 bucket**.
    + Đặt tên role name: ```AllowAccessS3InputOutput```
    + Chọn nút **Create job**.
![bathjob](/images/3.connect/006-batchTranslate.png)
{{% notice warning %}}
Nếu bạn đã chọn **Create job** và bị lỗi này thì do bạn chưa có file ở thư mục raw của input bucket. Bạn phải tải lên file cần dịch trước khi tạo job. 
{{% /notice %}}
![bathjob](/images/3.connect/007-batchTranslate.png)
6. Truy cập vào input bucket và vào thư mục raw, tải những file .txt bạn muốn dịch lên.
![bathjob](/images/3.connect/008-batchTranslate.png)
7. Nếu bạn đã tải file lên rồi mà vẫn lỗi thì đó là do trước đó bạn đã tạo IAM Role với tên đó rồi, để **Create job** thành công, bạn cần đặt tên role khác đi hoặc refresh lại trang để Translate biết role đã tồn tại và có thể sử dụng.
![bathjob](/images/3.connect/009-batchTranslate.png)
8. Sau khi bạn chọn **Create job** thì **job sẽ ở trạng thái in progress** cho đến khi hoàn thành job.
![bathjob](/images/3.connect/010-batchTranslate.png)
9. Bạn có thể xem trạng thái và các cấu hình ta đã làm khi bấm vào.
![bathjob](/images/3.connect/011-batchTranslate.png)

{{% notice note %}}
Amazon Translate không tính tiền nếu bạn chọn cùng 1 ngôn ngữ cho "source language" và "target language". Nếu bạn chọn chế độ "auto" tự động phát hiện ngôn ngữ thì bạn sẽ bị tính phí cho phần đó.
{{% /notice %}}

{{% notice tip %}}
Nên tạo S3 buckets và bỏ file cần dịch vào trước khi đưa URI vào translate job.
{{% /notice %}}

{{% notice note %}}
Nếu bạn gặp lỗi không tìm thấy S3 buckets thì có thể do bạn đã tạo S3 bucket đó ở một region khác với region chạy translate.
{{% /notice %}}