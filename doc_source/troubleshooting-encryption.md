# Troubleshooting DRM encryption<a name="troubleshooting-encryption"></a>

If the DRM system key server is unavailable when AWS Elemental MediaConvert requests keys, the console displays the following message: Key Server Unavailable\. 

Content key encryption adds another layer of complexity to your jobs\. If you run into problems on a job that has content key encryption enabled, remove the certificate ARN from your job settings and troubleshoot the job using clear key delivery\. When you have that working, reenter the certificate ARN, and then try the job again\. 

If you contact the [AWS Support Center](https://console.aws.amazon.com/support/home#/) for troubleshooting purposes, have the following information available:
+ Region that the job was run in
+ Job ID
+ Account ID
+ Name of your DRM solution provider
+ Any other details about the problem that you are having that might assist with troubleshooting