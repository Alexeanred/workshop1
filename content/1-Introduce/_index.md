---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
**Amazon Translate** is a Neural Machine Translation (MT) service that translates text between languages supported by the service. The service provides high-quality, affordable, and customizable language translations, allowing developers to translate company- and user-generated content or build applications that require support on many languages.
- Some popular use cases:
    - In companies, applications include meeting notes, technical reports,...
    - Translate emails, in-game chats, chats with customers,...
- Supports translation in over 75 languages.
- Input is text in UTF-8 format.
- Reference fee table:
| Translation Type                             | Pricing                       | Free Tier                                    |
|----------------------------------------------|-------------------------------|----------------------------------------------|
| Standard Text Translation                    | $15.00 per million characters | 2 million characters per month for 12 months |
| Batch Document Translation                   | $15.00 per million characters | 2 million characters per month for 12 months |
| Real-Time Document Translation (Text & HTML) | $15.00 per million characters | No Free Tier for this service                |
| Real-Time Document Translation (Docx)        | $30.00 per million characters | No Free Tier for this service                |
| Active Custom Translation                    | $60.00 per million characters | 500,000 characters per month for 2 months    |

**Amazon S3** is an object storage service that provides on-demand scalability, ensuring the highest level of data availability, security and performance.
- In this lab, S3 is used as a place to store documents before and after translation and as a "trigger" to run the "lambda function".

**AWS Lambda** is a "serverless compute" service that allows you to run applications without creating or managing servers. You organize your application into Lambda functions. Lambda functions run only when needed and are capable of auto-scaling. You only pay for the compute time you use — AWS doesn't charge you while your application is not running.
- In this lab, the "lambda function" is written in Python and will process the documents to best complete the translation process.

**Amazon Cloudwatch** is a "monitoring" service that monitors resources and applications running on AWS.
- In this lab, Cloudwatch is used to monitor the operation of the lambda function and S3 bucket, from there we can fix errors and debug to help the serverless architecture work better.

**AWS IAM** is a tool within AWS that allows you to securely control access to your AWS resources. You can use IAM to control authentication in the login process and authorization in resource usage.
- In this lab, IAM is used to manage user creation and granting rights and roles to users and also granting permissions to lambda functions.
