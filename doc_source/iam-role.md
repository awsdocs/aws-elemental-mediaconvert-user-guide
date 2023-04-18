# Set up IAM permissions<a name="iam-role"></a>

To run transcoding jobs with AWS Elemental MediaConvert, you need an IAM service role to allow MediaConvert access to your resources, such as your input files and the locations where your output files are stored\. 

Regardless of how you initially create your IAM service role, you can refine this role at any time using IAM\. For more information, see [Adding and removing IAM identity permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console) in the *IAM User Guide*\.

You can create your IAM service role in one of these ways:
+ In the MediaConvert console, with some restrictions on the permissions you grant\. For instructions, see [Creating a role in MediaConvert, configured](creating-the-iam-role-in-mediaconvert-configured.md)\.

  From the MediaConvert console, you can take the time to configure your role to allow MediaConvert access to only some of your Amazon S3 buckets and you can choose whether to grant invoke access to your API Gateway endpoints\.
+ In the IAM console\. For instructions, see [Creating a role in IAM](creating-the-iam-role-in-iam.md)\.

  You can exercise fine control over exactly what access you grant to MediaConvert when you set up your IAM role in the IAM console\. You can also use IAM through the AWS CLI, API, or SDK\.

**Note**  
If you enable Amazon S3 default encryption on your Amazon S3 buckets, and you and specify your own master key managed by AWS Key Management Service, you must grant additional permissions\. For more information, see [Granting permissions for MediaConvert to access encrypted S3 buckets](granting-permissions-for-mediaconvert-to-access-encrypted-s3-buckets.md)\.

**Setting up a default role**  
Regardless of how you create the IAM service role for MediaConvert to use, if you use the name MediaConvert\_Default\_Role, then the MediaConvert console uses it by default when you create jobs in the future\.