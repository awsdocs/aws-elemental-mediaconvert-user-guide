# Creating the IAM role in MediaConvert with full permissions<a name="creating-the-iam-role-in-mediaconvert-full"></a>

The easiest, fastest route to getting a job running with AWS Elemental MediaConvert is to set up the service role with full permissions to your Amazon Simple Storage Service \(S3\) buckets and your Amazon API Gateway endpoints\. The MediaConvert service uses only the permissions that it needs to run your job\.

**Note**  
 This approach doesn't follow the security best practice of least permissions\.

**To set up your MediaConvert role in MediaConvert, full permissions**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Get started**\.

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **AWS integration**\.

1. In the **Service access** section, for **Service role control**, choose **Create a new service role, full permissions**\.

1. For **New role name**, we suggest that you keep the default value **MediaConvert\_Default\_Role**\. When you do, MediaConvert uses this role by default for your future jobs\.

1. Continue to the next step of this tutorial, [Step 6: Create a job](create-a-job.md)\.