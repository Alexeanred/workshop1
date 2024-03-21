---
title : "Grant permissions to Lambda functions"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.3.2 </b> "
---

### Create Lambda role
1. Access IAM:
     + Select **Roles**.
     + Select the **Create role** button.
![lambdarole](/images/2.prerequisite/035-lambda.png)
2. In step 1:
     + Select **AWS service**.
     + In the **Use case** section, in **Service or use case**: Select **Lambda**.
     + Select the **Next** button.
![lambdarole](/images/2.prerequisite/036-lambda.png)
3. In Step 2:
     + Add the following permissions to the search bar and tick: ```AmazonS3FullAccess```, ```CloudWatchFullAccess```, ```TranslateFullAccess```.

![lambdarole](/images/2.prerequisite/037-lambda.png)

4. In Step 3:
     + Enter Role name: ```AllowLambdaFunctionWorkshop1```.
![lambdarole](/images/2.prerequisite/038-lambda.png)
5. Review the information and select the **Create role** button.

![lambdarole](/images/2.prerequisite/039-lambda.png)

### Assign roles to lambda functions
1. Access the lambda function again and choose a function to assign a role:
![lambdarole](/images/2.prerequisite/040-lambda.png)
2. After selecting **batchingFunction**:
     + select **Configuration**.
     + select **Permissions**.
     + select the **Edit** button.
![lambdarole](/images/2.prerequisite/041-lambda.png)
3. In Edit, in the **Existing role** section:
     + Select the newly created role name in IAM role: **AllowLambdaFunctionWorkshop1**.
     + Select the **Save** button.
![lambdarole](/images/2.prerequisite/042-lambda.png)
4. Check the Role name in that function and do the same with the remaining 2 functions.
![lambdarole](/images/2.prerequisite/043-lambda.png)
**You have completed the settings to use lambda functions.**