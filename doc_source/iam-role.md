# Step 3: Set up IAM permissions<a name="iam-role"></a>

To run transcoding jobs with AWS Elemental MediaConvert, first set up an AWS Identity and Access Management \(IAM\) role to allow MediaConvert access to your input files and the locations where your output files are stored\. If you use DRM, your IAM permissions also allow MediaConvert to access your encryption keys through API Gateway\.

**To set up your MediaConvert role in IAM**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane of the IAM console, choose **Roles**, and then choose **Create role**\.

1. Choose the **AWS service** role type, and then choose the **MediaConvert** service\.

1. Choose the **MediaConvert** use case for your service\. Then choose **Next: Permissions**\. The service has already defined the permissions used by the role\. These permissions grant MediaConvert the following permissions:
   + Full access to your Amazon S3 resources
   + API Gateway invoke full access

   The only entity that can assume this role is the MediaConvert service\.

1. Choose **Next: Review**\.

1. For **Role name**, enter a name that describes the purpose of the role\. If you use the name **MediaConvert\_Default\_Role**, then the MediaConvert console will use this role by default when you run jobs\.

   Role names must be unique within your AWS account\. You can use up to 64 characters that are letters, numbers, or any of the following: \+ = , \. @ \- \_

   Because various entities might reference the role, you can't edit the name of the role after it has been created\.

1. \(Optional\) For **Role description**, edit the description for the new service role\.

1. Review the role, and then choose **Create role**\.

**Note**  
When you [enable Amazon S3 default encryption](https://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html#bucket-encryption-how-to-set-up), Amazon S3 automatically encrypts your objects as you upload them\. You can optionally choose to use AWS Key Management Service \(KMS\) to manage the master key\. This is called SSE\-KMS encryption\.  
If you enable SSE\-KMS default encryption on the buckets that hold your AWS Elemental MediaConvert input or output files, you must also [add inline policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console) to this MediaConvert role\. Otherwise, MediaConvert can't read your input files or write your output files\. Grant these permissions:  
If your input bucket has SSE\-KMS default encryption, grant `kms:Decrypt`\.
If your output bucket has SSE\-KMS default encryption, grant `kms:GenerateDataKey`\.
This [example inline policy](example-inline-policy-kms-decrypt-generatedatakey.md) grants both permissions\.