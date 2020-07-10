# Step 4: Test your rule<a name="mediaconvert_sns_test_rule"></a>

To test your rule, submit a job that you know will cause an error\. For example, specify an input location that does not exist\. If you configured your event rule correctly, you should receive an email with the event text message in a few minutes\. 

**To test the rule**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Submit a new MediaConvert job\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Check the email account that you specified when you set up your Amazon SNS topic\. Confirm that you received an email notification for the job error\.