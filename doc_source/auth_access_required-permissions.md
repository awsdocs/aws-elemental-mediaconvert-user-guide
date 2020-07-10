# Permissions required<a name="auth_access_required-permissions"></a>

To use AWS Elemental MediaConvert or to manage authorization and access control for yourself or others, you must have the correct permissions\. 

## Permissions required to use the AWS Elemental MediaConvert console<a name="auth_access_required-permissions-console"></a>

To access the AWS Elemental MediaConvert console, you must have a minimum set of permissions that allows you to list and view details about the AWS Elemental MediaConvert resources in your AWS account\. If you create an identity\-based permissions policy that is more restrictive than the minimum required permissions, the console won't function as intended for entities with that policy\.

The following sample policy grants the IAM user permissions to all AWS Elemental MediaConvert actions \(such as `ListJobs`, `CreateJob`, and so on\) on all MediaConvert resources \(such as jobs, queues, and output presets\)\. It also grants the IAM actions required for the user to specify the service role that MediaConvert will assume in order to run the job\. It also grants Amazon S3 actions that allow the user to use the **Browse** button to choose input and output locations\. The Amazon S3 permissions aren't required to run the job; without them, the user can specify the URL of the bucket instead\. You can attach this policy to a user as described in the [Creating policies on the JSON tab](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-json-editor) topic of the *IAM User Guide*\.

```
{
  "Version": "2012-10-17",
  "Statement": [{
      "Sid": "mediaconvertActions",
      "Effect": "Allow",
      "Action": [
        "mediaconvert:*",
      ],
      "Resource": "arn:aws:mediaconvert:*:*:*"
    },
    {
      "Sid": "iamActions",
      "Effect": "Allow",
      "Action": [
        "iam:PassRole",
        "iam:ListRoles"
      ],
      "Resource": [
        "arn:aws:iam::*:role/*"
      ]
    },
    {
      "Sid": "s3Actions",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetBucketLocation",
        "s3:ListAllMyBuckets"
      ],
      "Resource": [
        "arn:aws:s3:::*"
      ]
    }
  ]
}
```

## Permissions required for authorization management<a name="auth_access_required-permissions-iam-auth"></a>

To manage your own credentials, such as your password, access keys, and multi\-factor authentication \(MFA\) devices, your administrator must grant you the required permissions\. 

As an AWS administrator, you need full access to IAM so that you can create and manage users, groups, roles, and policies in IAM\. You should use the [AdministratorAccess](https://console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AdministratorAccess) AWS managed policy that includes full access to all of AWS\. This policy does not provide access to the AWS Billing and Cost Management console or allow tasks that require root user credentials\. For more information, see [AWS tasks that require AWS Account Root User credentials](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html) in the *AWS General Reference*\.

**Warning**  
Only an administrator user should have full access to AWS\. Anyone with this policy has permission to fully manage authentication and access control, in addition to modifying every resource in your AWS account\.

## Permissions required for access control<a name="auth_access_required-permissions-iam-authz"></a>

If your administrator provided you with IAM user credentials, they attached policies to your IAM user identity to control what resources you can access\. To view the policies attached to your user identity in the AWS Management Console, you must have the following permissions:

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
            "Resource": [
                "arn:aws:iam::*:user/${aws:username}"
            ]
        },
        {
            "Sid": "ListUsersViewGroupsAndPolicies",
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

If you need additional permissions, ask your administrator to update your policies to allow you to access the actions that you require\.