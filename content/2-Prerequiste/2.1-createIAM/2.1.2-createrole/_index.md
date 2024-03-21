---
title : "Create workshop role"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Create Role

1. In page IAM:
  + Choose item **Roles**.
  + Choose button **Create role**.
![role](/images/2.prerequisite/007-role.png)

2. In Step 1:
  + Choose **AWS account**.
  + Choose **This account**.
  + Click button **Next**.
![role](/images/2.prerequisite/008-role.png)

3. In Step 2:
  + **Copy these policy names**, go to the search bar and tick select:
    + ```AmazonS3FullAccess```
    + ```AWSLambda_FullAccess```
    + ```CloudWatchFullAccess```
    + ```IAMFullAccess```
    + ```TranslateFullAccess```
  + Click button **Next**.
![role](/images/2.prerequisite/009-role.png)

4. In step 3:
  + Type role name: ```workshop1-role```.
  + Review the **Trust policy** to see if the role is allowed on this account.
![role](/images/2.prerequisite/010-role.png)

5. Review the rights you have granted to the role through policy names.
  + Add tags if needed and select the button **Create role**.
![role](/images/2.prerequisite/011-role.png)
**You have finished creating roles for workshop users.**
