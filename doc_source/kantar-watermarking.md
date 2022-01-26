# Using Kantar for audio watermarking in AWS Elemental MediaConvert outputs<a name="kantar-watermarking"></a>

Kantar is a company that provides and tracks unique identifiers for media content in the form of audio watermarks that are audible to machines but not to humans\. After you establish a relationship with Kantar, you can use AWS Elemental MediaConvert to encode these watermarks into your content, for audience measurement and anti\-piracy applications\.

To use MediaConvert to encode Kantar watermarks, you use AWS Secrets Manager to store your Kantar credentials\. These credentials are the user name and password that you set up with Kantar\. Then you grant the MediaConvert service permission to read those credentials, so that MediaConvert can communicate with the Kantar servers to request your watermarks and to provide log information\. In your MediaConvert job, uou provide your Kantar license information and information about the media asset that you're encoding\. For more information about these steps, see the following topics\.

**Topics**
+ [Getting a Kantar watermarking license](getting-a-kantar-watermarking-license.md)
+ [Storing your Kantar credentials in AWS Secrets Manager](storing-your-kantar-credentials-in-secrets-manager.md)
+ [Granting IAM permissions to your Kantar credentials](granting-permissions-for-mediaconvert-to-access-secrets-manager-secret.html.md)
+ [Setting up your MediaConvert job for Kantar watermarking](setting-up-your-job-for-kantar-watermarking.md)