---
title : "Quá trình Combine"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

![architecture-serverless](/images/arc-clean.png)

### Tổng quan
+ Quá trình combine được diễn ra cuối cùng để ghép các files đã dịch ở **translated bucket** thành 1 file như file gốc.
+ Nhận events đã có files đã dịch xong, combine function sẽ xử lý, gộp lại các files để thành 1 file và trả về **Final Translated bucket**.

### Nội dung
+ [Thêm trigger](4.3.1-trigger/) 
+ [Cấu hình function](4.3.2-function/)