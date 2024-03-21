---
title : "Cấu hình Batching function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.1.2 </b> "
---
1. Ở batching function:
  + Trong phần **Code**:
    + Nhập vào đoạn code sau:
  ```python
  import boto3
  import json
  import os

  s3 = boto3.client('s3')

  MAX_CHARS = 9500


  def lambda_handler(event, context):
      print(json.dumps(event, indent=2))

      output_bucket = os.environ.get('OutputBucket')
      if not output_bucket:
          return print('Error: OutputBucket not defined')

      for record in event['Records']:
          try:
              do_batching(record, output_bucket)
          except Exception as e:
              print(f'Handler error: {e}')


  def split_into_sentences(text):
      sentences = []
      start = 0
      for i, char in enumerate(text):
          if char in ['.', '!', '?'] and i > 0 and text[i - 1] not in ['.', '!', '?']:
              sentences.append(text[start:i + 1])
              start = i + 1
      if start < len(text):
          sentences.append(text[start:])
      return sentences


  def do_batching(event, output_bucket):
      original_text = s3.get_object(
          Bucket=event['s3']['bucket']['name'],
          Key=event['s3']['object']['key']
      )
      print('Downloaded object from S3')

      text = original_text['Body'].read().decode('utf-8')
      print(f'Original text length: {len(text)}')

      sentences = split_into_sentences(text)

      counter = 0
      while sentences:
          counter += 1
          batch_text = ''
          while sentences and len(batch_text) + len(sentences[0]) <= MAX_CHARS:
              batch_text += sentences.pop(0) + ' '

          new_key = event['s3']['object']['key'].replace('.txt', f'-{counter}.txt')
          result = s3.put_object(
              Bucket=output_bucket,
              Key=new_key,
              Body=batch_text.strip(),
              ContentType='text/plain'
          )

          print(f'S3 result: {json.dumps(result, indent=2)}')


  # Entry point for local testing
  if __name__ == '__main__':
      sample_event = {
          "Records": [
              {
                  "s3": {
                      "bucket": {
                          "name": "example-bucket"
                      },
                      "object": {
                          "key": "example.txt"
                      }
                  }
              }
          ]
      }
      lambda_handler(sample_event, None)
  ```
  + Giải thích:
    + Giới hạn số ký tự 1 file không quá 9500 ký tự.
    + Tạo hàm để chia đoạn văn thành các câu.
    + Sau đó, gộp các câu lại và trả về các files ở batched bucket.
  + Sau đó, chọn nút **Deploy** để hàm cập nhật đoạn code mới nhất.
![batchingfunc](/images/4.s3/004-batching.png)

2. Sau đó, vào mục **Configuration**:
  + Chọn **Environment variables**.
  + Chọn nút **Edit**.
![batchingfunc](/images/4.s3/006-batching.png)
3. Trong Environment variables:
  + Chọn nút: **Add environment variable**.
  + Ở **Key**: nhập ```OutputBucket```.
  + Ở **Value**: nhập  ```batched-bucket-<your_id>```.
  + Chọn nút **Save**.
![batchingfunc](/images/4.s3/007-batching.png)
4. Để test hàm vừa tạo:
  + Chọn nút **test**.  
  + Chọn **Create new event**.
  + Event name: nhập **test**
  + Trong **Event JSON**:
    + Nhập:
  ```json
  {
    "Records": [
      {
        "s3": {
          "bucket": {
            "name": "batching-bucket-<your_id>"
          },
          "object": {
            "key": "IELST-reading2.txt"
          }
        }
      }
    ]
  }
  ```
  + Ở trên: **bucket name** là tên bucket ta tải file dịch lên (batching bucket), **object key** là file ta đã tải lên muốn dịch.
  + Chọn nút **Save** và sau đó bạn có thể test được.
![batchingfunc](/images/4.s3/005-batching.png)
5. Sau khi test xong, bạn có thể truy cập vào cloudwatch để xem log của request ta gửi test:
  + Chọn mục **Monitor**.
  + Chọn **View Cloudwatch logs**.
![batchingfunc](/images/4.s3/008-batching.png)
6. Chọn mục **log streams** để xem log và refresh nếu có log mới gửi vào.
![batchingfunc](/images/4.s3/009-batching.png)

**Hooray!!! Bạn đã cấu hình xong batching function.**