# Setting the priority of a job<a name="setting-the-priority-of-a-job"></a>

You can specify a job's place in a queue by setting its priority in the job settings when you create the job\. AWS Elemental MediaConvert processes jobs in each queue in order of priority, starting with the highest number\. If more than one job has the highest value for priority, MediaConvert chooses among them by selecting the one that you submitted first\.

MediaConvert doesn't stop the current job when you submit a job with a higher priority\. When the running job is finished, MediaConvert starts the next job based on its relative priority in the queue\.

**To set the priority for a job \(console\)**

1. Set up your job as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, in the **Job settings** section, choose **Settings**\.

1. In the **Job settings** section on the right, for **Priority**, enter a number from \-50 to 50\. MediaConvert processes jobs with the highest value for **Priority** first\. If you don't specify a value, MediaConvert assigns the default value of 0\.

**To set the priority for a job \(API, SDK, and AWS CLI\)**

1. Set up your JSON job specification\. Either manually edit your JSON file, or use the console to generate it as follows:

   1. Follow the previous procedure for the console\.

   1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

   The JSON job specification has the value for the job's priority in the property `priority`\. This property is a direct child of `job`, which is the top level of the JSON job specification\. Set the value of `priority` to an integer in the range from \-50 to 50, inclusive\. The default value is 0\.

1. Submit your job according to the instructions in the *AWS Elemental MediaConvert API Reference\.*
   + If you're using one of the AWS SDKs or the AWS CLI, see [Getting started with MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)\.
   + If you're calling the MediaConvert API directly, see [Getting started with MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)\.