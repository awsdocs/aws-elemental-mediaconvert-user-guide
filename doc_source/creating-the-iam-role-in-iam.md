# Creating the IAM role in IAM<a name="creating-the-iam-role-in-iam"></a>

Working directly with IAM, you can do actions that aren't available in the MediaConvert console\. You can either do this when you create your role in IAM, or you can create your role in MediaConvert and then use IAM to refine it later\.

The following procedure explains how to set up the role using the IAM console\. For information about accessing IAM programmatically, see the appropriate document in the [IAM documentation set](https://docs.aws.amazon.com/iam/)\.

**To set up your MediaConvert role in IAM \(console\)**

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