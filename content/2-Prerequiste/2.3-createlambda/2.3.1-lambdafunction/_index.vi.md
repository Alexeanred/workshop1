---
title : "Tạo Lambda functions"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.3.1 </b> "
---

### Tạo lambda function
1. Trong console, vào thanh tìm kiếm, nhập **lambda**:
![lambdafunc](/images/2.prerequisite/031-lambda.png)
2. Sau khi vào lambda, chọn nút **Create function**.
![lambdafunc](/images/2.prerequisite/032-lambda.png)
3. Trong **Create function**:
    + Chọn **Author from stratch**.
    + Nhập tên function: ```batchingFunction```.
    + Chọn Runtime: **Python 3.12**.
    + Chọn architecture: **_x86_64**.
    + Chọn nút **Create function**.
![lambdafunc](/images/2.prerequisite/033-lambda.png)
4. Làm tương tự 3 bước trên để tạo được 3 functions sau:
    + ```batchingFunction```
    + ```translateFunction```
    + ```combineFunction```
![lambdafunc](/images/2.prerequisite/034-lambda.png)
**Như vậy, ta đã tạo được các lambda functions, bước tiếp theo là tạo role để lambda có quyền truy cập các tài nguyên khác.**
