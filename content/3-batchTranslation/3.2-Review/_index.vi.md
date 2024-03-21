---
title : "Xem kết quả và cách chạy lại job"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

### Xem kết quả
1. Sau khi chạy xong job, thì status sẽ chuyển sang **Completed**.
    + Lúc này bạn có thể vào S3 bucket output để xem thành quả.
![bathjob](/images/3.connect/012-batchTranslate.png)
2. Khi vào S3 bucket output, chọn thư mục output.
![bathjob](/images/3.connect/013-batchTranslate.png)
3. Chọn thư mục bắt đầu bằng id account của mình: 
![bathjob](/images/3.connect/014-batchTranslate.png)
4. Chọn 1 file đã được dịch:
    + Dịch sang tiếng Việt nên đầu file là **vi**.
![bathjob](/images/3.connect/015-batchTranslate.png)
5. Bấm vào nút **Open** hoặc **Download** để xem.
![bathjob](/images/3.connect/016-batchTranslate.png)

### Cách chạy lại job
1. Vào lại job ở Batch Translation:
    + Chọn nút **Copy**.
![bathjob](/images/3.connect/017-batchTranslate.png)
2. Nó sẽ tự động cấu hình lại job như cũ và tên có thêm chữ **copy**
    + Bạn có thể sử dụng lại role cũ nếu muốn dùng 2 buckets cũ.
![bathjob](/images/3.connect/018-batchTranslate.png)