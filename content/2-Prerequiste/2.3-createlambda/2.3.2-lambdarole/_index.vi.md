---
title : "Cấp quyền cho Lambda functions"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.3.2 </b> "
---

### Tạo Lambda role
1. Truy cập vào IAM:
    + Chọn mục **Roles**.
    + Chọn nút **Create role**.
![lambdarole](/images/2.prerequisite/035-lambda.png)
2. Trong step 1:
    + Chọn **AWS service**.
    + Tại mục **Use case**, trong **Service or use case**: Chọn **Lambda**.
    + Chọn nút **Next**.
![lambdarole](/images/2.prerequisite/036-lambda.png)
3. Trong Step 2:
    + Thêm các permissions sau vào thanh tìm kiếm và tick vào: ```AmazonS3FullAccess```, ```CloudWatchFullAccess```, ```TranslateFullAccess```.

![lambdarole](/images/2.prerequisite/037-lambda.png)

4. Trong Step 3:
    + Nhập Role name: ```AllowLambdaFunctionWorkshop1```.
![lambdarole](/images/2.prerequisite/038-lambda.png)
5. Review lại các thông tin và chọn nút **Create role**.

![lambdarole](/images/2.prerequisite/039-lambda.png)

### Gán role vào lambda functions
1. Truy cập lại vào lambda function và chọn 1 function để gán role:
![lambdarole](/images/2.prerequisite/040-lambda.png)
2. Sau khi chọn **batchingFunction**:
    + chọn mục **Configuration**.
    + chọn mục **Permissions**.
    + chọn nút **Edit**.
![lambdarole](/images/2.prerequisite/041-lambda.png)
3. Trong Edit, tại mục **Existing role**:
    + Chọn role name vừa tạo ở IAM role: **AllowLambdaFunctionWorkshop1**.
    + Chọn nút **Save**.
![lambdarole](/images/2.prerequisite/042-lambda.png)
4. Kiểm tra lại Role name ở function đó và làm tương tự với 2 functions còn lại.
![lambdarole](/images/2.prerequisite/043-lambda.png)
**Bạn đã hoàn thành xong các thiết lập để dùng lambda functions.**