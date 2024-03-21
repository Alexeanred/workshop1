---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
**Amazon Translate** là dịch vụ Neural Machine Translation (MT) để dịch văn bản giữa các ngôn ngữ được dịch vụ hỗ trợ. Dịch vụ cung cấp bản dịch ngôn ngữ chất lượng cao, giá cả phải chăng và có thể tùy chỉnh, cho phép các nhà phát triển dịch nội dung do công ty và người dùng tạo ra hoặc xây dựng các ứng dụng yêu cầu hỗ trợ trên nhiều ngôn ngữ.
- Một số use cases phổ biến: 
    - Trong công ty ứng dụng vào ghi chép cuộc họp, báo cáo kỹ thuật,...
    - Dịch email, đoạn chat trong game, đoạn chat với khách hàng,...
- Hỗ trợ dịch trên 75 ngôn ngữ.
- Đầu vào là những văn bản có định dạng UTF-8.
- Bảng phí tham khảo:
| Translation Type                             | Pricing                       | Free Tier                                    |
|----------------------------------------------|-------------------------------|----------------------------------------------|
| Standard Text Translation                    | $15.00 per million characters | 2 million characters per month for 12 months |
| Batch Document Translation                   | $15.00 per million characters | 2 million characters per month for 12 months |
| Real-Time Document Translation (Text & HTML) | $15.00 per million characters | No Free Tier for this service                |
| Real-Time Document Translation (Docx)        | $30.00 per million characters | No Free Tier for this service                |
| Active Custom Translation                    | $60.00 per million characters | 500,000 characters per month for 2 months    |

**Amazon S3** là một dịch vụ lưu trữ dạng đối tượng (object) cung cấp khả năng mở rộng theo yêu cầu sử dụng, đảm bảo tính khả dụng của dữ liệu, độ bảo mật và hiệu năng ở mức cao nhất.
- Trong bài này S3 được dùng như một nơi chứa tài liệu trước khi và sau khi dịch và là 1 "trigger" để chạy "lambda function".

**AWS Lambda** là một dịch vụ "serverless compute" cho phép bạn chạy ứng dụng mà không cần khởi tạo hoặc quản lý máy chủ. Bạn tổ chức ứng dụng của mình thành các Lambda function. Lambda function chỉ chạy khi cần thiết và có khả năng tự động mở rộng quy mô. Bạn chỉ phải trả cho thời gian tính toán mà bạn sử dụng — AWS sẽ không tính phí khi ứng dụng của bạn không chạy.
- Trong bài này làm "lambda function" được viết bằng ngôn ngữ Python và sẽ xử lý những tài liệu để quá trình dịch hoàn thành tốt nhất.

**Amazon Cloudwatch** là 1 dịch vụ "monitoring" giám sát những tài nguyên và ứng dụng chạy trên AWS.
- Trong bài này Cloudwatch dùng để theo dõi quá trình hoạt động của lambda function và S3 bucket, từ đó ta có thể sửa lỗi, debug giúp cho kiến trúc serverless hoạt động tốt hơn.

**AWS IAM** là một công cụ trong AWS cho phép bạn kiểm soát truy cập vào các tài nguyên AWS của bạn một cách an toàn. Bạn có thể sử dụng IAM để kiểm soát quá trình xác thực (authentication) trong quá trình đăng nhập và quá trình ủy quyền (authorization) trong việc sử dụng tài nguyên.
- Trong bài này IAM dùng để quản lý việc tạo user và cấp quyền, role cho user và cả cấp quyền cho lambda function.

