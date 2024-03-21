---
title : "Batching process"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

![architecture-serverless](/images/arc-clean.png)

### Overview
| Description                               | Limit        |
|-------------------------------------------|--------------|
| Character encoding                        | UTF-8        |
| Maximum input text                        | 10,000 bytes |
| Maximum number of characters per document | 100,000      |

+ Amazon Translate real-time limit is 10,000 bytes equivalent to 10 Kb per API call.

+ So in order not to exceed the size limit, we must divide files over 10 Kb into smaller ones.

+ The batching process helps us do that, one file can be divided into many files.

+ The user will upload files to the **Batching bucket**, the **Batching function** receives events, processes and returns the files to the **Batched bucket**.
### Content
+ [Add trigger](4.1.1-trigger/)
+ [Function configuration](4.1.2-function/)