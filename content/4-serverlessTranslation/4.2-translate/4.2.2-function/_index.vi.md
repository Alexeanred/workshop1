---
title : "Cấu hình Translate function"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2.2 </b> "
---
1. Ở translate function:
  + Trong phần **Code**:
    + Nhập vào đoạn code sau:
  ```python
  import boto3
  import os
  import json
  s3_client = boto3.client('s3')
  translate = boto3.client('translate')

  def translate_text(text, lang_code):
      result = translate.translate_text(
          Text=text,
          SourceLanguageCode='auto',
          TargetLanguageCode=lang_code
      )
      return result['TranslatedText']

  def lambda_handler(event, context):
      for record in event['Records']:
          bucket_name = record['s3']['bucket']['name']
          file_key = record['s3']['object']['key']
          output_bucket = os.environ.get('OutputBucket') # Output bucket for translated files

          print(f"Translating file: {file_key}")

          # Get the object from S3
          obj = s3_client.get_object(Bucket=bucket_name, Key=file_key)
          text = obj['Body'].read().decode('utf-8')

          # Translate the text
          translated_text = translate_text(text, 'vi')

          # Upload translated content to S3
          output_key = f"translated_{file_key}"  # You may want to adjust the naming convention
          s3_client.put_object(Body=translated_text.encode('utf-8'), Bucket=output_bucket, Key=output_key)

          print(f"Translation completed for {file_key}")

      print("All files translated and uploaded to S3")
  ```
  + Giải thích:
    + Tạo 1 hàm để dịch đoạn văn qua việc gọi API của translate
    + Hàm lambda_handler được dùng để nhận events và xử lý nó để kết quả xuất hiện ở **translated bucket**.
  + Sau đó, chọn nút **Deploy** để hàm cập nhật đoạn code mới nhất.
![translatefunc](/images/4.s3/004-translate.png)

2. Sau đó, vào mục **Configuration**:
  + Chọn **Environment variables**.
  + Chọn nút **Edit**.
![translatefunc](/images/4.s3/005-translate.png)
3. Trong Environment variables:
  + Chọn nút: **Add environment variable**.
  + Ở **Key**: nhập ```OutputBucket```.
  + Ở **Value**: nhập  ```translated-bucket-<your_id>```.
  + Chọn nút **Save**.
![translatefunc](/images/4.s3/006-translate.png)
4. Để test hàm vừa tạo:
  + Chọn nút **test**.  
  + Chọn **Create new event**.
  + Event name: nhập **test**
  + Trong **Event JSON**:
    + Nhập:
```
{
  "Records": [
    {
      "s3": {
        "bucket": {
          "name": "batched-bucket-<your_id>"
        },
        "object": {
          "key": "IELST-reading2-1.txt"
        }
      }
    }
  ]
}
```
  + Ở trên: **bucket name** là tên bucket ta có những file đã qua quá trình batching (batched bucket), **object key** là 1 file trong bucket đó.
  + Chọn nút **Save** và sau đó bạn có thể test được.
![translatefunc](/images/4.s3/007-translate.png)
5. Sau khi test xong, bạn có thể truy cập vào cloudwatch để xem log của request ta gửi test:
  + Chọn mục **Monitor**.
  + Chọn **View Cloudwatch logs**.
![translatefunc](/images/4.s3/008-translate.png)
6. Chọn mục **log streams** để xem log và refresh nếu có log mới gửi vào.
![translatefunc](/images/4.s3/009-translate.png)

**Hooray!!! Bạn đã cấu hình xong translate function.**
