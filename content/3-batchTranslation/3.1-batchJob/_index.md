---
title : "Create batch translation job"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

1. In the console, in the search bar, enter ```Translate```.
![bathjob](/images/3.connect/001-batchTranslate.png)
2. In the Translate interface:
     + Select **Batch translation**.
     + Select the **Create job** button.
![bathjob](/images/3.connect/002-batchTranslate.png)
3. In **Create Translate Job**:
     + In the **Name** section, enter ```MyTranslateJob```.
     + Select source language: **English**.
     + Select target language: **Vietnamese**.
![bathjob](/images/3.connect/003-batchTranslate.png)
4. In the Input data section:
     + Select the **Select folder** button.
     + Access the directory path in the input bucket: **s3://translate-job-batch-input-150903/raw/**.
     + Select File format: **Plain text (.txt)**.
     + Access the directory path in the output bucket: **s3://translate-job-batch-output-150903/output/**.
     + Your data is encrypted by default.
![bathjob](/images/3.connect/005-batchTranslate.png)
5. We must grant Translate permission to access S3 buckets:
     + Select to create a new IAM role **Create an IAM role**.
     + In the IAM role section: Select **Input and output S3 buckets** if you want to only give Translate access to these 2 buckets.
     + If you want all buckets, select **Any S3 bucket**.
     + Name the role name: ```AllowAccessS3InputOutput```
     + Select the **Create job** button.
![bathjob](/images/3.connect/006-batchTranslate.png)
{{% notice warning %}}
If you have selected **Create job** and get this error, it is because you do not have a file in the raw directory of the input bucket. You must upload the file to be translated before creating a job.
{{% /notice %}}
![bathjob](/images/3.connect/007-batchTranslate.png)
6. Access the input bucket and go to the raw folder, download the .txt files you want to translate.
![bathjob](/images/3.connect/008-batchTranslate.png)
7. If you have uploaded the file and still have the error, it is because you have previously created an IAM Role with that name. To **Create job** successfully, you need to name the role differently or refresh the page to Translate knows the role exists and can be used.
![bathjob](/images/3.connect/009-batchTranslate.png)
8. After you select **Create job**, the **job will be in progress** status until the job is completed.
![bathjob](/images/3.connect/010-batchTranslate.png)
9. You can see the status and configurations we have made when you click.
![bathjob](/images/3.connect/011-batchTranslate.png)

{{% notice note %}}
Amazon Translate does not charge you if you select the same language for "source language" and "target language". If you select the "auto" mode that automatically detects the language, you will be charged for that portion.
{{% /notice %}}

{{% notice tip %}}
You should create S3 buckets and put the files to be translated before putting the URI into the translate job.
{{% /notice %}}

{{% notice note %}}
If you get an error that S3 buckets cannot be found, it may be because you created that S3 bucket in a different region than the region where translate is running.
{{% /notice %}}