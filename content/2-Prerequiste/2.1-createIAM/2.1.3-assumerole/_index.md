---
title : "Grant permissions to the user assume role"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Grant permissions to the user

1. Access the user **workshop-1-user** just created:
  + Select the **Add permissions** button.
  + Select **Create inline policy**.

![assume](/images/2.prerequisite/012-assume.png)

2. In Step 1:
  + Select **JSON**.
  + Copy and paste the following lines:
```
  {
    "Version": "2012-10-17",
    "Statement": {
        "Effect": "Allow",
        "Action": "sts:AssumeRole",
        "Resource": [
            "arn:aws:iam::<your_AWS_account_id>:role/workshop1-role",
        ]
    }
}
```
  + Click button **Next**.
{{% notice note %}}
Replace **<your_AWS_account_id>** with your id. For example: arn:aws:iam::030444900838:role/workshop1-role.
{{% /notice %}}

![assume](/images/2.prerequisite/013-assume.png)

3. In Step 2:
  + Enter Policy name: **AssumeRoleWorkshop1**.
  + Select the **Create policy** button.

![assume](/images/2.prerequisite/014-assume.png)

You have completed **granting permission to the user assume role**, the final step is to **log in to the user and change to the role for the workshop**.
