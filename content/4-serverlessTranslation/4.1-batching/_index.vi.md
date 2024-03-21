---
title : "Quá trình Batching"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

![architecture-serverless](/images/arc-clean.png)

### Tổng quan
| Description                               | Limit        |
|-------------------------------------------|--------------|
| Character encoding                        | UTF-8        |
| Maximum input text                        | 10,000 bytes |
| Maximum number of characters per document | 100,000      |

+ Amazon Translate real-time giới hạn 10,000 bytes tương đương 10 Kb trên một API call.

+ Nên để không vượt quá giới hạn về size, ta phải chia những file trên 10 Kb nhỏ hơn.

+ Quá trình batching giúp ta làm được điều đó, 1 file có thể chia thành nhiều files.

+ Người dùng sẽ tải files lên vào **Batching bucket**, **Batching function** nhận events, xử lý và trả những files về **Batched bucket**.
### Nội dung
+ [Thêm trigger](4.1.1-trigger/) 
+ [Cấu hình function](4.1.2-function/)