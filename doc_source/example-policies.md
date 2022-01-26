# Example policies<a name="example-policies"></a>

Use these example IAM policies to grant access to your resources, or modify them to suit your use case\. For information about how to attach a policy to an IAM user, see [Creating policies on the JSON tab](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-json-editor) in the *IAM User Guide*\.

## Example policy: Basic MediaConvert user policy<a name="example-policy-basic-mediaconvert-user-policy"></a>

The following example policy grants the basic permissions that a user needs to operate AWS Elemental MediaConvert\. In this example, the account number is *111122223333* and the role name is *MediaConvertRole*\. If you are using encryption, or if your Amazon S3 buckets have default encryption enabled, you need additional permissions\. For more information, see [Protecting your media assets with encryption and DRM using AWS Elemental MediaConvert](using-encryption.md)\.

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

The following policy grants the user access to all actions on all MediaConvert resources in the account, unless the action listed under `DenyMediaConvertWithResourceTag` is tagged with the key `access` and has a value `denied` or a value that starts with the string "`deny`"\.

**Note**  
This policy demonstrates the IAM principle that, in the case where user policies both allow and deny action on a resource, the denial takes precedence\. Therefore, the user with this attached policy can't perform the denied actions, even if they have a different policy that allows administrative permissions to all MediaConvert resources\.

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