# Creating the IAM role in MediaConvert with configured permissions<a name="creating-the-iam-role-in-mediaconvert-configured"></a>

This approach allows you to restrict the access that you grant MediaConvert to only specific S3 buckets, and to specify whether to allow invoke access to your Amazon API Gateway endpoints\.

**To set up your MediaConvert role in MediaConvert, configured permissions**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Get started**\.

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **AWS integration**\.

1. In the **Service access** section, for **Service role control**, choose **Create a new service role, configure permissions**\.

1. For **New role name**, we suggest that you keep the default value **MediaConvert\_Default\_Role**\. When you do, MediaConvert uses this role by default for your future jobs\.

1. For **Input S3 locations** and **Output S3 locations**, choose **Add location**\. Select the S3 buckets that you created in the previous step of this tutorial, [Create storage for files](set-up-file-locations.md)\.

1. Optional\. If you use features that require it, for **API Gateway enpoint invocation**, choose allow\.

   MediaConvert requires this access for the following features:
   + Digital rights management with SPEKE
   + Nielsen non\-linear watermarking

   If you prefer to allow MediaConvert invoke access only to a specific endpoint, you can modify these permissions in the role policy after you create it, using the AWS Identity and Access Management \(IAM\) service\. For more information, see [Editing IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-edit.html) in the *AWS Identity and Access Management User Guide*\.