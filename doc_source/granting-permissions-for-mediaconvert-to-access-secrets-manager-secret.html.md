# Granting IAM permissions to your Kantar credentials<a name="granting-permissions-for-mediaconvert-to-access-secrets-manager-secret.html"></a>

When you use AWS Elemental MediaConvert, you specify an IAM service role that grants permissions to the service to access the resources it needs to run your job\. For example, your MediaConvert service role grants MediaConvert permissions to read your job input files from Amazon S3\. For information about setting up that service role, see [Set up IAM permissions ](iam-role.md)\.

To encode Kantar watermarks, add permissions to this service role to grant MediaConvert access to read the AWS Secrets Manager secret that holds your Kantar credentials\.

**To grant MediaConvert permission to read your Kantar credentials**

1. Create a policy that grants permission to read your Secrets Manager secret\.

   1. Make sure that you have the ARN to the Secrets Manager secret that you created in the previous topic\.

   1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

   1. In the navigation pane on the left, under **Access management**, choose **Policies**\.

   1. Choose **Create policy**\.

   1. On the **Create policy** page, next to **Service**, choose **Choose a service**\.

   1. In the search field, type **secrets** and then choose **Secrets Manager** from the results\.

   1. In the **Filter actions** search field, type **GetSecretValue** and then choose **GetSecretValue** from the results\.

   1. In the **Resources** section, next to **Secret**, choose **Add ARN**\.

   1. On the **Add ARN\(s\)** page, next to **Specify ARN for Secret**, choose **List ARNs manually**\.

   1. In the **Type or paste a list of ARNs** section, paste the ARN for your Kantar credentials secret that you copied at the end of the procedure in the previous topic\.

   1. Choose **Add**\.

   1. At the bottom of the **Create policy** page, choose **Next: Tags**\.

   1. Choose **Next: Review**\.

   1. Under **Review policy**, for **Name** type a name that will help you remember the purpose of this policy, such as **GetKantarCreds**\.

   1. Optionally, for **Description**, jot a note to yourself for later\. For example, you might write "This provides MediaConvert permission to read my Kantar credentials\."

   1. Choose **Create policy**\.

1. Attach the policy to your MediaConvert role\.

   1. In the navigation pane on the left, under **Access management**, choose **Roles**\.

   1. From the list of roles, choose the name of the role that you use with your MediaConvert job\. This role is often **MediaConvert\_Default\_Role**\.

   1. On the role **Summary** page, on the **Permissions** tab, choose **Attach policies**\.

   1. In the search field, type the name of the policy you created, such as **GetKantarCreds**\.

   1. In the results list, choose the check box next to the policy name\.

   1. Choose **Attach policy**\.

   1. On the **Summary** page for the role, review the list of policies and confirm that your policy that grants permission to get your Kantar credentials appears there\.