---
title : "Configure Translate function"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2.2 </b> "
---
1. In translate function:
   + In the **Code** section:
     + Enter the following code:
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
+ Explanation:
     + Create a function to translate the paragraph by calling the translate API
     + The lambda_handler function is used to receive events and process them so that the results appear in the **translated bucket**.
   + Then, select the **Deploy** button to have the function update to the latest code.
![translatefunc](/images/4.s3/004-translate.png)

2. Then, go to **Configuration**:
   + Select **Environment variables**.
   + Select the **Edit** button.
![translatefunc](/images/4.s3/005-translate.png)
3. In Environment variables:
   + Select the button: **Add environment variable**.
   + In **Key**: enter ```OutputBucket```.
   + In **Value**: enter ```translated-bucket-<your_id>```.
   + Select the **Save** button.
![translatefunc](/images/4.s3/006-translate.png)
4. To test the newly created function:
   + Select the **test** button.
   + Select **Create new event**.
   + Event name: enter **test**
   + In **Event JSON**:
     + Enter:
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
   + Above: **bucket name** is the name of the bucket we have files that have gone through the batching process (batched bucket), **object key** is a file in that bucket.
   + Select the **Save** button and then you can test.
![translatefunc](/images/4.s3/007-translate.png)
5. After testing, you can access cloudwatch to view the log of the request we sent to test:
   + Select **Monitor**.
   + Select **View Cloudwatch logs**.
![translatefunc](/images/4.s3/008-translate.png)
6. Select **log streams** to view the log and refresh if there is a new log sent in.
![translatefunc](/images/4.s3/009-translate.png)

**Hooray!!! You have finished configuring the translate function.**
