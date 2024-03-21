---
title : "View results"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4 </b> "
---

1. Upload a paragraph of AWS Blogs from your computer:
   + The paragraph has 3056 characters so when batching it is still 1 file.
![testing](/images/4.s3/008-testing.png)
2. Go to **batching-bucket-<your_id>**:
   + Select the **Upload** button
![testing](/images/4.s3/002-testing.png)
3. Check before uploading:
   + File has a capacity of 3 KB.
   + Select the **Upload** button
![testing](/images/4.s3/003-testing.png)
4. After success, there will be a green line:
![testing](/images/4.s3/004-testing.png)
5. Then, go to bucket **final-translated-bucket-<your_id>**:
   + Select the file with the word **translated** at the beginning and the file name after it.
![testing](/images/4.s3/005-testing.png)
6. Download and check the translated blog.
![testing](/images/4.s3/007-testing.png)
**Ok, so we have successfully translated a blog paragraph from English to Vietnamese.**

{{% notice note %}}
You can still upload 2 documents at the same time and it will still return 2 translated files for those 2 documents. Please try it.
{{% /notice %}}