---
title : "Quá trình Translate"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---


![architecture-serverless](/images/arc-clean.png)

### Tổng quan
+ Sau khi nhận events là đã có objects được put vào bucket **batched-bucket**.
+ **Translation function** sẽ gửi đoạn văn (text) trong những files đó đến Amazon Translate để dịch, sau đó, API của Amazon translate sẽ trả về đoạn văn đã dịch. 
+ Các files đã dịch được put vào **Translated bucket**.

### Nội dung
+ [Thêm trigger](4.2.1-trigger/) 
+ [Cấu hình function](4.2.2-function/)