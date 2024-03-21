---
title : "Translate documents with asynchronous Batch Translation"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

### Introducing asynchronous batch translation
+ Asynchronous refers to tasks that do not happen at the same time, batch is a collection of objects/files.

+ Asynchronous batch translation is a form of translation provided by Amazon Translate to translate multiple documents at the same time (total size up to 5GB).

+ Each document must not exceed 20 MB.

+ No more than 1 million characters per document.

+ No more than 1 million documents per batch.

+ We will create a job to ask Amazon Translate to translate for us, the results will then be saved in the S3 bucket.

### Content
+ [Create batch job](3.1-batchJob/)
+ [See results](3.2-Review/)