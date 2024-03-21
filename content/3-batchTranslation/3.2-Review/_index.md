---
title : "See the results and how to run the job again"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

### See results
1. After running the job, the status will change to **Completed**.
     + Now you can go to the S3 output bucket to see the results.
![bathjob](/images/3.connect/012-batchTranslate.png)
2. When entering the S3 output bucket, select the output folder.
![bathjob](/images/3.connect/013-batchTranslate.png)
3. Select the folder starting with your account id:
![bathjob](/images/3.connect/014-batchTranslate.png)
4. Select a translated file:
     + Translated into Vietnamese so the beginning of the file is **vi**.
![bathjob](/images/3.connect/015-batchTranslate.png)
5. Click the **Open** or **Download** button to view.
![bathjob](/images/3.connect/016-batchTranslate.png)

### How to rerun job
1. Go back to the job in Batch Translation:
     + Select the **Copy** button.
![bathjob](/images/3.connect/017-batchTranslate.png)
2. It will automatically reconfigure the job as before and the name has the word **copy** added
     + You can reuse the old role if you want to use 2 old buckets.
![bathjob](/images/3.connect/018-batchTranslate.png)