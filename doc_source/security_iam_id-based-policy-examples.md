# Identity\-based policy examples for AWS Elemental MediaConvert<a name="security_iam_id-based-policy-examples"></a>

By default, users and roles don't have permission to create or modify MediaConvert resources\. They also can't perform tasks by using the AWS Management Console, AWS Command Line Interface \(AWS CLI\), or AWS API\. To grant users permission to perform actions on the resources that they need, an IAM administrator can create IAM policies\. The administrator can then add the IAM policies to roles, and users can assume the roles\.

To learn how to create an IAM identity\-based policy by using these example JSON policy documents, see [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html) in the *IAM User Guide*\.

For details about actions and resource types defined by MediaConvert, including the format of the ARNs for each of the resource types, see [Actions, resources, and condition keys for AWS Elemental MediaConvert](https://docs.aws.amazon.com/service-authorization/latest/reference/mediaconvert.html) in the *Service Authorization Reference*\.

**Topics**
+ [Policy best practices](#security_iam_service-with-iam-policy-best-practices)
+ [Using the MediaConvert console](#security_iam_id-based-policy-examples-console)
+ [Allow users to view their own permissions](#security_iam_id-based-policy-examples-view-own-permissions)
+ [Example policy: Basic MediaConvert policy](#example-policy-basic-mediaconvert-user-policy)
+ [Example policy: Resource\-level access control](#example-policy-resource-level-access-control)
+ [Example policy: Tag\-based access control using resource tags](#example-policy-tag-based-access-control-using-resource-tags)

## Policy best practices<a name="security_iam_service-with-iam-policy-best-practices"></a>

Identity\-based policies determine whether someone can create, access, or delete MediaConvert resources in your account\. These actions can incur costs for your AWS account\. When you create or edit identity\-based policies, follow these guidelines and recommendations:
+ **Get started with AWS managed policies and move toward least\-privilege permissions** – To get started granting permissions to your users and workloads, use the *AWS managed policies* that grant permissions for many common use cases\. They are available in your AWS account\. We recommend that you reduce permissions further by defining AWS customer managed policies that are specific to your use cases\. For more information, see [AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies) or [AWS managed policies for job functions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html) in the *IAM User Guide*\.
+ **Apply least\-privilege permissions** – When you set permissions with IAM policies, grant only the permissions required to perform a task\. You do this by defining the actions that can be taken on specific resources under specific conditions, also known as *least\-privilege permissions*\. For more information about using IAM to apply permissions, see [ Policies and permissions in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) in the *IAM User Guide*\.
+ **Use conditions in IAM policies to further restrict access** – You can add a condition to your policies to limit access to actions and resources\. For example, you can write a policy condition to specify that all requests must be sent using SSL\. You can also use conditions to grant access to service actions if they are used through a specific AWS service, such as AWS CloudFormation\. For more information, see [ IAM JSON policy elements: Condition](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html) in the *IAM User Guide*\.
+ **Use IAM Access Analyzer to validate your IAM policies to ensure secure and functional permissions** – IAM Access Analyzer validates new and existing policies so that the policies adhere to the IAM policy language \(JSON\) and IAM best practices\. IAM Access Analyzer provides more than 100 policy checks and actionable recommendations to help you author secure and functional policies\. For more information, see [IAM Access Analyzer policy validation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-policy-validation.html) in the *IAM User Guide*\.
+ **Require multi\-factor authentication \(MFA\)** – If you have a scenario that requires IAM users or a root user in your AWS account, turn on MFA for additional security\. To require MFA when API operations are called, add MFA conditions to your policies\. For more information, see [ Configuring MFA\-protected API access](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html) in the *IAM User Guide*\.

For more information about best practices in IAM, see [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) in the *IAM User Guide*\.

## Using the MediaConvert console<a name="security_iam_id-based-policy-examples-console"></a>

To access the AWS Elemental MediaConvert console, you must have a minimum set of permissions\. These permissions must allow you to list and view details about the MediaConvert resources in your AWS account\. If you create an identity\-based policy that is more restrictive than the minimum required permissions, the console won't function as intended for entities \(users or roles\) with that policy\.

You don't need to allow minimum console permissions for users that are making calls only to the AWS CLI or the AWS API\. Instead, allow access to only the actions that match the API operation that they're trying to perform\.

To ensure that users and roles can still use the MediaConvert console, also attach the MediaConvert `ConsoleAccess` or `ReadOnly` AWS managed policy to the entities\. For more information, see [Adding permissions to a user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_change-permissions.html#users_change_permissions-add-console) in the *IAM User Guide*\.

The following sample policy grants the IAM user permissions to all AWS Elemental MediaConvert actions \(such as `ListJobs`, `CreateJob`, and so on\) on all MediaConvert resources \(such as jobs, queues, and output presets\)\. It also grants the IAM actions required for the IAM user to specify the service role that MediaConvert will assume in order to run the job\. It also grants Amazon S3 actions that allow the IAM user to use the **Browse** button to choose input and output locations\. The Amazon S3 permissions aren't required to run the job; without them, the IAM user can specify the URL of the bucket instead\. In this example, the account number is *111122223333* and the role name is *MediaConvertRole*\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "mediaconvertActions",
      "Effect": "Allow",
      "Action": "mediaconvert:*",
      "Resource": "*"
    },
    {
      "Sid": "iamListRoles",
      "Effect": "Allow",
      "Action": "iam:ListRoles",
      "Resource": "*"
    },
    {
      "Sid": "iamPassRole",
      "Effect": "Allow",
      "Action": "iam:PassRole",
      "Resource": "arn:aws:iam::111122223333:role/MediaConvertRole"
    },
    {
      "Sid": "s3Actions",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetBucketLocation",
        "s3:ListAllMyBuckets"
      ],
      "Resource": "*"
    }
  ]
}
```

## Allow users to view their own permissions<a name="security_iam_id-based-policy-examples-view-own-permissions"></a>

This example shows how you might create a policy that allows IAM users to view the inline and managed policies that are attached to their user identity\. This policy includes permissions to complete this action on the console or programmatically using the AWS CLI or AWS API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ViewOwnUserInfo",
            "Effect": "Allow",
            "Action": [
                "iam:GetUserPolicy",
                "iam:ListGroupsForUser",
                "iam:ListAttachedUserPolicies",
                "iam:ListUserPolicies",
                "iam:GetUser"
            ],
            "Resource": ["arn:aws:iam::*:user/${aws:username}"]
        },
        {
            "Sid": "NavigateInConsole",
            "Effect": "Allow",
            "Action": [
                "iam:GetGroupPolicy",
                "iam:GetPolicyVersion",
                "iam:GetPolicy",
                "iam:ListAttachedGroupPolicies",
                "iam:ListGroupPolicies",
                "iam:ListPolicyVersions",
                "iam:ListPolicies",
                "iam:ListUsers"
            ],
            "Resource": "*"
        }
    ]
}
```

## Example policy: Basic MediaConvert policy<a name="example-policy-basic-mediaconvert-user-policy"></a>

The following example policy grants the basic permissions to operate AWS Elemental MediaConvert\. In this example, the account number is *111122223333* and the role name is *MediaConvertRole*\. If you are using encryption, or if your Amazon S3 buckets have default encryption enabled, you need additional permissions\. For more information, see [Protecting your media assets with encryption and DRM using AWS Elemental MediaConvert](using-encryption.md)\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "mediaconvertActions",
      "Effect": "Allow",
      "Action": "mediaconvert:*",
      "Resource": "*"
    },
    {
      "Sid": "iamListRoles",
      "Effect": "Allow",
      "Action": "iam:ListRoles",
      "Resource": "*"
    },
    {
      "Sid": "iamPassRole",
      "Effect": "Allow",
      "Action": "iam:PassRole",
      "Resource": "arn:aws:iam::111122223333:role/MediaConvertRole"
    },
    {
      "Sid": "s3Actions",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetBucketLocation",
        "s3:ListAllMyBuckets"
      ],
      "Resource": "*"
    }
  ]
}
```

## Example policy: Resource\-level access control<a name="example-policy-resource-level-access-control"></a>

The following example policy grants permissions to certain AWS Elemental MediaConvert resources in your account\. In this example, the account number is *012345678910*\. It allows the following actions, in any partition and Region:
+ View the details of all queues in the account at once\.
+ View all the jobs that have been submitted to the queue "myQueue" at once\.
+ Create a job and submit it to the queue "myQueue", referencing any presets with names that start with "allow" and referencing any job template\.
+ Create a job template referencing the queue "myQueue" and any presets with names that start with "allow"\.

**Note**  
You can't grant cross\-account permissions to AWS Elemental MediaConvert resources, such as queues, output presets, and jobs\. You can grant cross\-account permissions to your input and output media files stored in Amazon S3\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowListQueues",
            "Effect": "Allow",
            "Action": "mediaconvert:ListQueues",
            "Resource": "*"
        },
        {
            "Sid": "AllowListJobsInQueue",
            "Effect": "Allow",
            "Action": "mediaconvert:ListJobs",
            "Resource": "arn:*:mediaconvert:*:012345678910:queues/myQueue"
        },
        {
            "Sid": "AllowCreateLimitedJobs",
            "Effect": "Allow",
            "Action": [
                "mediaconvert:CreateJob",
                "mediaconvert:CreateJobTemplate"
            ],
            "Resource": [
                "arn:*:mediaconvert:*:012345678910:queues/myQueue",
                "arn:*:mediaconvert:*:012345678910:presets/allow*",
                "arn:*:mediaconvert:*:012345678910:jobTemplates/*"
            ]
        }
    ]
}
```

## Example policy: Tag\-based access control using resource tags<a name="example-policy-tag-based-access-control-using-resource-tags"></a>

The following policy grants access to all actions on all MediaConvert resources in the account, unless the action listed under `DenyMediaConvertWithResourceTag` is tagged with the key `access` and has a value `denied` or a value that starts with the string "`deny`"\.

**Note**  
This policy demonstrates the IAM principle that, in the case where policies both allow and deny action on a resource, the denial takes precedence\. Therefore, the IAM user with this attached policy can't perform the denied actions, even if they have a different policy that allows administrative permissions to all MediaConvert resources\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowMediaConvert",
            "Effect": "Allow",
            "Action": "mediaconvert:*",
            "Resource": "*"
        },
        {
            "Sid": "DenyMediaConvertWithResourceTag",
            "Effect": "Deny",
            "Action": [
                "mediaconvert:DeleteJobTemplate",
                "mediaconvert:GetQueue",
                "mediaconvert:UpdateQueue",
                "mediaconvert:DeleteQueue",
                "mediaconvert:GetPreset",
                "mediaconvert:ListTagsForResource",
                "mediaconvert:GetJobTemplate",
                "mediaconvert:UntagResource",
                "mediaconvert:UpdateJobTemplate",
                "mediaconvert:DeletePreset",
                "mediaconvert:TagResource",
                "mediaconvert:UpdatePreset"
            ],
            "Resource": "*",
            "Condition": {
                "StringLike": {
                    "aws:ResourceTag/access": [
                        "deny*",
                        "denied"
                    ]
                }
            }
        }
    ]
}
```