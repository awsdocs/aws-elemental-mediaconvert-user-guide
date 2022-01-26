# Storing your Kantar credentials in AWS Secrets Manager<a name="storing-your-kantar-credentials-in-secrets-manager"></a>

After you establish a relationship with Kantar, store your Kantar user name and password in an AWS Secrets Manager secret\. You can find a step\-by\-step tutorial in the topic [Create and store your secret in AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/tutorials_basic.html#tutorial-basic-step1) in the *AWS Secrets Manager User Guide\.*

**To store your Kantar credentials in a Secrets Manager secret**

Follow the tutorial linked in the introduction to this procedure, with the following differences\.

1. Make sure that you use the same AWS Region for Secrets Manager that you use for your MediaConvert job\.

1. In the **Specify key/value pairs to be stored in the secret** section, set up two key\-value pairs\. One holds your Kantar login name and the other holds your password\.  
![\[This screenshot shows two key-value pairs. The key for the first is "login" and the value is your Kantar login name. The key for the second is "password" and the value is your Kantar password.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/kantar-secret-ASM.png)

   1. Type **login** in the left field and then type your Kantar login name in the right field\.

   1. Choose **Add row** to bring up a second pair of entry fields\.

   1. Type **password** in the left field and then type your Kantar password in the right field\.

   The plaintext version of your secret should look like this: `{ "login": "KantarLogin", "password": "KantarPassword" }`, where KantarLogin is the user name for your Kantar credentials and KantarPassword is the password for your Kantar credentials\.

1. In the **Secret name and description** section, for **Secret name**, use a name that you will associate with Kantar, such as **KantarCreds**\.
**Note**  
You provide the name of this secret in your MediaConvert job settings\.

1. For **Description**, you might want to note that this is the secret that you use with MediaConvert for encoding your Kantar watermarks\.

1. After you store the secret, copy the ARN of your secret to use when you grant IAM permissions to MediaConvert to access the secret\.

   1. On the Secrets Manager **Secrets** page, choose the name of your secret\.

   1. Copy and save the string you see listed under **Secret ARN**\.
**Note**  
You use this ARN when you grant MediaConvert permissions to get this secret\.