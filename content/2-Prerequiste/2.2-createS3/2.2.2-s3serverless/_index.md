---
title : "Create S3 buckets for serverless translation"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2.2 </b> "
---

### Create s3 buckets for serverless translation

1. In S3, select the **Create bucket** button to create a new bucket:
![s3serverless](/images/2.prerequisite/044-serverless.png)
2. In Create Bucket:
   + Select AWS Region: **Singapore (ap-southeast-1)**.
   + Enter bucket name: ```batching-bucket-<your_id>```. For example: batching-bucket-150903.
{{% notice tip %}}
Choose your own id so it doesn't overlap with the names of other buckets on Amazon S3.
{{% /notice %}}
![s3serverless](/images/2.prerequisite/045-serverless.png)
3. Leave other parameters as default, select **Create Bucket** button.
![s3serverless](/images/2.prerequisite/046-serverless.png)
4. Do the same as the 3 steps above to successfully create 4 buckets as follows:
   + ```batching-bucket-<your_id>```
   + ```batched-bucket-<your_id>```
   + ```translated-bucket-<your_id>```
   + ```final-translated-bucket-<your_id>```
![s3serverless](/images/2.prerequisite/047-serverless.png)

**Hooray! You have finished creating S3 buckets, next prepare the lambda functions.**

