# Step 3: Set Up IAM Permissions<a name="iam-role"></a>

To run transcoding jobs with MediaConvert, first set up an AWS Identity and Access Management \(IAM\) role to allow MediaConvert access to your input files and the locations where your output files are stored\. If you use DRM, your IAM permissions also allow MediaConvert to access your encryption keys through API Gateway\.

**To set up your MediaConvert role in IAM**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane of the IAM console, choose **Roles**, and then choose **Create role**\.

1. Choose the **AWS service** role type, and then choose the **MediaConvert** service\.

1. Choose the **MediaConvert** use case for your service\. Then choose **Next: Permissions**\. The service has already defined the permissions used by the role\. These permissions grant MediaConvert the following permissions:
   + Full access to your Amazon S3 resources
   + API Gateway invoke full access

   The only entity that can assume this role is the MediaConvert service\.

1. Choose **Next: Review**\.

1. For **Role name**, type a name that describes the purpose of the role\. You might want to begin the name with "MediaConvert" to make it easy to find when you are creating a job\.

   Role names must be unique within your AWS account\. You can use up to 64 characters that are letters, numbers, or any of the following: \+ = , \. @ \- \_

   Because various entities might reference the role, you cannot edit the name of the role after it has been created\.

1. \(Optional\) For **Role description**, edit the description for the new service role\.

1. Review the role, and then choose **Create role**\.