---
title : "Configure Batching function"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.1.2 </b> "
---
1. In batching function:
   + In the **Code** section:
     + Enter the following code:
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
+ Explanation:
     + Limit the number of characters per file to no more than 9500 characters.
     + Create a function to divide paragraphs into sentences.
     + Then, combine the sentences and return the files to the batched bucket.
   + Then, select the **Deploy** button to have the function update to the latest code.
![batchingfunc](/images/4.s3/004-batching.png)

2. Then, go to **Configuration**:
   + Select **Environment variables**.
   + Select the **Edit** button.
![batchingfunc](/images/4.s3/006-batching.png)
3. In Environment variables:
   + Select the button: **Add environment variable**.
   + In **Key**: enter ```OutputBucket```.
   + In **Value**: enter ```batched-bucket-<your_id>```.
   + Select the **Save** button.
![batchingfunc](/images/4.s3/007-batching.png)
4. To test the newly created function:
   + Select the **test** button.
   + Select **Create new event**.
   + Event name: enter **test**
   + In **Event JSON**:
     + Enter:
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
   + Above: **bucket name** is the name of the bucket we uploaded the translation file to (batching bucket), **object key** is the uploaded file we want to translate.
   + Select the **Save** button and then you can test.
![batchingfunc](/images/4.s3/005-batching.png)
5. After testing, you can access cloudwatch to view the log of the request we sent to test:
   + Select **Monitor**.
   + Select **View Cloudwatch logs**.
![batchingfunc](/images/4.s3/008-batching.png)
6. Select **log streams** to view the log and refresh if there is a new log sent in.
![batchingfunc](/images/4.s3/009-batching.png)

**Hooray!!! You have finished configuring the batching function.**