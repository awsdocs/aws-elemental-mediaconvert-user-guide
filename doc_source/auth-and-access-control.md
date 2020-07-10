# Authentication and access control for AWS Elemental MediaConvert<a name="auth-and-access-control"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS Elemental MediaConvert resources\. Administrators use IAM to control who is *authenticated* \(signed in\) and *authorized* \(has permissions\) to use MediaConvert resources\. IAM is a feature of your AWS account offered at no additional charge\.

When you use AWS Elemental MediaConvert, you typically interact with two different kinds of resources:
+ **Media files** – The media files that are inputs to and outputs from AWS Elemental MediaConvert are Amazon S3 resources, not MediaConvert resources\. The MediaConvert service must have permissions to access these files, but the user submitting the job doesn't need permissions to access them\.
+ **MediaConvert resources** – The AWS Elemental MediaConvert service uses resources such as jobs, queues, output presets, and job templates to transcode your media files\. MediaConvert implicitly has permissions to these resources\. The person creating and submitting MediaConvert jobs must have explicit permissions to access them\.

To use AWS Elemental MediaConvert, you must set up a minimum of two IAM entities:
+ **User** – The person setting up and submitting the job signs on to AWS Elemental MediaConvert as an IAM *user*\. To access your MediaConvert resources, the user must belong to your AWS account\.

  You set up this user identity and grant it permissions when you are signed on to IAM as your account root user or as a user with administrative privileges\. For more information about the permissions that you need to grant to this MediaConvert user, see [Permissions required to use the AWS Elemental MediaConvert console](auth_access_required-permissions.md#auth_access_required-permissions-console)\.
+ **Service role** – The AWS Elemental MediaConvert service assumes an IAM role in order to access your input media files and to write your output media files\. Depending on how you use MediaConvert, you might also need to grant some permissions to your Amazon API Gateway and AWS Key Management Service \(AWS KMS\) resources\. You create this service role in your AWS account while signed on to IAM as your account root user or as a user with administrative privileges\. You choose this role when you are signed on to MediaConvert as a user\. 

  For information about creating this service role, see [Step 3: Set up IAM permissions ](iam-role.md) of the *Getting Started* chapter of this guide\.

  For general information about service roles, see [Creating a role to delegate permissions to an AWS service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html) in the *IAM User Guide*\. 

**Topics**
+ [Introduction to authorization and access control](auth_access_introduction.md)
+ [Permissions required](auth_access_required-permissions.md)
+ [Understanding how AWS Elemental MediaConvert works with IAM](auth_access_service-with-iam.md)
+ [Troubleshooting authentication and access control](auth_access_troubleshoot.md)
+ [Example policies](example-policies.md)