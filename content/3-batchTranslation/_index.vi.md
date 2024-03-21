---
title : "Dịch tài liệu với asynchronous Batch Translation"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

### Giới thiệu về asynchronous batch translation
+ Asynchronous chỉ những công việc xảy ra không cùng lúc, batch là 1 tập hợp các objects/files.

+ Asynchronous batch translation là 1 dạng dịch được Amazon Translate cung cấp để dịch nhiều tài liệu cùng 1 lúc (tổng size lên đến 5GB).

+ Mỗi tài liệu không quá 20 MB.

+ Không quá 1 triệu ký tự mỗi tài liệu.

+ Không quá 1 triệu tài liệu mỗi batch.

+ Ta sẽ tạo 1 job để yêu cầu Amazon Translate dịch cho ta, kết quả sau đó được lưu trong S3 bucket.

### Nội dung
+ [Tạo batch job](3.1-batchJob/) 
+ [Xem kết quả](3.2-Review/)