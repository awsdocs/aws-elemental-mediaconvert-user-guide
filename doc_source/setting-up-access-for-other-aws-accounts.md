# Setting up access for other AWS accounts to your AWS Elemental MediaConvert outputs<a name="setting-up-access-for-other-aws-accounts"></a>

When you follow the usual setup for permissions as described in [Step 3: Set up IAM permissions ](iam-role.md), only users that belong to your AWS account can access your output files\.

In some cases, you might want to allow users of other AWS accounts access to the outputs of your jobs\. For example, you might run transcoding jobs on behalf of one of your customers, and you might want that customer to have access to the outputs of the jobs\. You can do this in one of the following ways:
+ **Grant access to your Amazon S3 bucket\.**

  When you do this, MediaConvert writes your output files to your bucket, and you grant another account access to your bucket\.
+ **Have MediaConvert write your output files to a bucket owned by another account\. **

  You can have MediaConvert apply an Amazon S3 canned access control list \(ACL\) to your outputs\. A canned ACL is a predefined ACL that includes the necessary permissions\.

  When you do this, you still own the output file, but MediaConvert grants access to the outputs to the owner of the bucket\.

**Topics**
+ [Granting access to your output Amazon S3 bucket](granting-access-to-your-output-amazon-s3-bucket.md)
+ [Writing your outputs to an Amazon S3 bucket in another account](write-your-outputs-to-another-accounts-amazon-s3-bucket.md)