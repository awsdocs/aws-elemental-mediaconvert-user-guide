# Introduction to authorization and access control<a name="auth_access_introduction"></a>

To work with AWS services and resources, you need both *authentication* and *access control*\.

**Authentication** – To sign in to AWS, you must use credentials: root user credentials \(not recommended\), IAM user credentials, or temporary credentials using IAM roles\. To learn more about these entities, see [What is authentication?](auth_access_what-is-authentication.md)\.

**Access control** – AWS administrators use policies to control access to AWS resources, such as an AWS Elemental MediaConvert job\. To learn more, see [What is access control?](auth_access_what-is-access-control.md) and [What are policies?](auth_access_what-are-policies.md)\.

**Important**  
All resources in an account are owned by the account, regardless of who created those resources\. A user must be granted access to create a resource\. However, just because a user creates a resource doesn't mean that the user automatically has full access to that resource\. An administrator must explicitly grant permissions for each action that each user wants to perform\. That administrator can also revoke these permissions at any time\.

**Ownership of Media Files and AWS Elemental MediaConvert Jobs**  
When you use your AWS account to create an AWS Elemental MediaConvert job and to create Amazon S3 buckets for your input and output files, your AWS account is the owner of the job and the output files created by the job\. This has the following implications:
+ Any user in your account with permissions to access your Amazon S3 objects can access the output files of your job\.
+ Only an administrator on your account can grant permissions to access these output files\.
+ Only users in your account can receive permissions to access the job object\.

If you want to set up your workflow so that the outputs of your job are owned by another account—for example, by the account of one of your customers—then the administrator of the other account must grant you cross\-account permissions to write to their Amazon S3 bucket\. In this setup, your AWS account owns the job resource, but not the outputs of the job\. For more information, see [Access management](https://docs.aws.amazon.com/IAM/latest/UserGuide/access.html) in the *IAM User Guide*\.

**Understanding the Basics of IAM**  
To help you understand the basics of how IAM works, review the following terms:
+ **Resources** – AWS services, such as AWS Elemental MediaConvert, Amazon S3, and IAM, are made up of objects called resources\. You can create, manage, and delete these resources from the service\. IAM resources include users, groups, roles, and policies: 
  + **Users** – An IAM user represents the person or application that uses its credentials to interact with AWS\. A user consists of a name, a password to sign in to the AWS Management Console, and up to two access keys that can be used with the AWS CLI or AWS API\.
  + **Groups** – An IAM group is a collection of IAM users\. You can use groups to specify permissions for its member users\. This makes it easier for you to manage permissions for multiple users\.
  + **Roles** – An IAM role doesn't have any long\-term credentials \(password or access keys\) associated with it\. A role can be assumed by anyone who has the right permissions\. An IAM user can assume a role to temporarily take on different permissions for a specific task\. Federated users can assume a role by using an external identity provider that is mapped to the role\. Some AWS services can assume a *service role* to access AWS resources on your behalf\.
  + **Policies** – Policies are JSON policy documents that define the permissions for the object that they are attached to\. AWS supports *identity\-based policies* that you attach to identities \(users, groups, or roles\)\. Some AWS services allow you to attach *resource\-based policies* to resources to control what a principal \(person or application\) can do with that resource\. AWS Elemental MediaConvert does not support resource\-based policies\.
+ **Identities** – Identities are IAM resources for which you can define permissions\. These include users, groups, and roles\.
+ **Entities** – Entities are IAM resources that you use for authentication\. These include users and roles\. 
+ **Principals** – In AWS, a principal is a person or application that uses an entity to sign in and make requests to AWS\. As a principal, you can use the AWS Management Console, the AWS CLI, or the AWS API to perform an operation \(such as deleting a job\)\. This creates a *request* for that operation\. Your request specifies the *action*, *resource*, *principal*, *principal account*, and any additional information about your request\. All of this information provides AWS with *context* for your request\. AWS checks all the policies that apply to the context of your request\. AWS authorizes the request only if each part of your request is allowed by the policies\. 

To view a diagram of the authentication and access control process, see [Understanding how IAM works](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html) in the *IAM User Guide*\. For details about how AWS determines whether a request is allowed, see [Policy evaluation logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html) in the *IAM User Guide*\.