---
title : "Clean up lab resources"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

### S3
#### **Delete created buckets**
We need to delete 4 buckets: **batching-bucket, batched-bucket, translated-bucket, final-translated-bucket**.

Follow these 4 steps to delete a bucket. Do the same for the remaining 3 buckets.
1. Go to a created bucket:
   + Delete objects (files) first.
   + Select all files.
   + Select the **Delete** button.
![clean](/images/5.fwd/001-cleanup.png)
2. Enter **permanently delete**
   + Select the **Delete objects** button.
![clean](/images/5.fwd/002-cleanup.png)
3. Exit to S3 interface:
   + Select the bucket you want to delete.
   + Select the **Delete** button
![clean](/images/5.fwd/003-cleanup.png)
4. Enter the name of the bucket you want to delete to confirm.
   + Select **Delete bucket**.
![clean](/images/5.fwd/004-cleanup.png)
### Lambda
We need to delete 3 functions: **batchingFunction, combineFunction, translationFunction**.

Follow these 2 steps to delete a function. Do the same for the remaining 2 functions.
1. Select a bucket to delete.
   + Go to **Actions**.
   + Select **Delete**
![clean](/images/5.fwd/005-cleanup.png)

2. Type ```delete```.
   + Select the **Delete** button.
![clean](/images/5.fwd/011-cleanup.png)
### Translate
In **Batch translation**, we cannot delete a completed job.

It only has 3 buttons **Copy** to copy the current job, **Stop** to stop a running job, **Create job** to create a new job.
![clean](/images/5.fwd/006-cleanup.png)

### Cloudwatch
1. Access **Cloudwatch**:
   + Select **Log groups**.
   + Select the log of a function we created.
![clean](/images/5.fwd/007-cleanup.png)
2. In the **log streams** section:
   + Select all logs.
   + Select the **Delete** button.
![clean](/images/5.fwd/008-cleanup.png)

### IAM
#### Delete the user we created:
   + Select user: **workshop-1-user**.
   + Select the **Delete** button.
   + Enter the user name again to confirm.
   + Select the **Delete user** button.
![clean](/images/5.fwd/009-cleanup.png)
#### Delete the role we created:
   + Select role: **workshop1-role**.
   + Select the **Delete** button.
   + Enter the role name again to confirm.
   + Select the **Delete** button.
  
There are also other roles we have created, you can do the same to delete them.
![clean](/images/5.fwd/010-cleanup.png)