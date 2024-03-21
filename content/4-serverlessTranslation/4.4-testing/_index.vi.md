---
title : "Xem kết quả"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4 </b> "
---

1. Tải lên 1 đoạn văn của AWS Blogs từ máy tính:
  + Đoạn văn có 3056 ký tự nên khi batching thì nó vẫn là 1 file.
![testing](/images/4.s3/008-testing.png)
2. Vào **batching-bucket-<your_id>**:
  + Chọn nút **Upload**
![testing](/images/4.s3/002-testing.png)
3. Kiếm tra trước khi upload:
  + File có lưu lượng 3 KB.
  + Chọn nút **Upload**
![testing](/images/4.s3/003-testing.png)
4. Sau khi thành công sẽ có 1 dòng màu xanh:
![testing](/images/4.s3/004-testing.png)
5. Sau đó, bạn vào bucket **final-translated-bucket-<your_id>**:
  + Chọn file có chữ **translated** ở đầu và tên file ở sau.
![testing](/images/4.s3/005-testing.png)
6. Tải về và kiểm tra blog đã dịch xong.
![testing](/images/4.s3/007-testing.png)
**Ok, vậy ta đã dịch thành công 1 đoạn blog từ tiếng Anh sang Việt rồi.**

{{% notice note %}}
Bạn vẫn có thể tải lên 2 tài liệu cùng 1 lúc và nó vẫn trả về 2 files đã dịch cho 2 tài liệu đó. Bạn hãy thử xem nhé.
{{% /notice %}}