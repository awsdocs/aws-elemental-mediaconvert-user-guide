# Creating the IAM role in IAM<a name="creating-the-iam-role-in-iam"></a>

Working directly with IAM, you can do actions that aren't available in the MediaConvert console\. You can either do this when you create your role in IAM, or you can create your role in MediaConvert and then use IAM to refine it later\.

The following procedure explains how to set up the role using the IAM console\. For information about accessing IAM programmatically, see the appropriate document in the [IAM documentation set](https://docs.aws.amazon.com/iam/)\.

**To create the service role for AWS Elemental MediaConvert \(IAM console\)**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane of the IAM console, choose **Roles**, and then choose **Create role**\.

1. Choose the **AWS service** role type, and then choose AWS Elemental MediaConvert\.

1. Choose the MediaConvert use case\. Then, choose **Next**\.

1. Select the box next to the the MediaConvert policy that you created in the previous procedure\.

1. \(Optional\) Set a [permissions boundary](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)\. This is an advanced feature that is available for service roles, but not service\-linked roles\. 

   Expand the **Permissions boundary** section and choose **Use a permissions boundary to control the maximum role permissions**\. IAM includes a list of the AWS managed and customer managed policies in your account\. Select the policy to use for the permissions boundary or choose **Create policy** to open a new browser tab and create a new policy from scratch\. For more information, see [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html#access_policies_create-start) in the *IAM User Guide*\. After you create the policy, close that tab and return to your original tab to select the policy to use for the permissions boundary\.

1. Choose **Next**\.

1. If possible, enter a role name or role name suffix to help you identify the purpose of this role\. Role names must be unique within your AWS account\. They are not distinguished by case\. For example, you cannot create roles named both **PRODROLE** and **prodrole**\. Because various entities might reference the role, you cannot edit the name of the role after it has been created\.

1. \(Optional\) For **Description**, enter a description for the new role\.

1. Choose **Edit** in the **Step 1: Select trusted entities** or **Step 2: Select permissions** sections to edit the use cases and permissions for the role\. 

1. \(Optional\) Add metadata to the role by attaching tags as key\-value pairs\. For more information about using tags in IAM, see [Tagging IAM resources](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_tags.html) in the *IAM User Guide*\.

1. Review the role and then choose **Create role**\.