# Monitoring AWS Elemental MediaConvert<a name="monitoring-overview"></a>

You can track a job's progress, including the status, phase, and percentage of completion\. For information, see [Monitoring MediaConvert job progress](how-mediaconvert-jobs-progress.md)\.

You can monitor the *status* of your jobs and their percent completion in these places:

**AWS Elemental MediaConvert jobs page**  
The [MediaConvert console](https://console.aws.amazon.com/mediaconvert) shows the following details about your jobs: **Job ID**, **Queue**, **Status**, **Submit time**, **Start Time**, **Transcode duration**, **Job percent complete**, **Finish time**, **Warnings**, **Inputs**, **First input file name**, **First input file path**, **Output groups**, and **First output group destination**\.  
Optionally, you can filter jobs according to **Status** or **Queue**\.

**Amazon EventBridge**  
With EventBridge, you can get more detailed information about the status of your jobs, including any API calls, percent completion of the probing, transcoding, and uploading phases\. AWS Elemental MediaConvert sends these events to the default event bus in the EventBridge service\. You can create rules to monitor MediaConvert programmatically using other AWS services\. For more information, see [Using Amazon EventBridge with MediaConvert](eventbridge_events.md)\.

MediaConvert emits metrics, events, and warnings data \(when applicable\) when a job completes\. You can use this data to evaluate the success of a job, even if it completes without error\. Data that can be used to evaluate a job, or even a trend in multiple jobs, can be found in these places:

**MediaConvert Jobs page**  
In the MediaConvert console, you can see your job completion status and view any warnings that may have occurred while transcoding\. For more granular information, such as QVBR video quality statistics, instead use EventBridge\.

**MediaConvert API**  
Through the MediaConvert API, you can request a list of jobs, job status, and job details\. For more information, see [Jobs](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html) in the *AWS Elemental MediaConvert API Reference*\. 

**Amazon CloudWatch metrics**  
With Amazon CloudWatch, you can view trends in transcoding statistics across your completed jobs, including QVBR video quality\. MediaConvert emits transcode statistics to CloudWatch at the end of every job\.  
For more information about using MediaConvert with CloudWatch metrics, see [Using CloudWatch with MediaConvert](cloudwatch_metrics.md)\.

**Amazon EventBridge**  
With EventBridge, you can get more detailed information about the result of your completed jobs\. MediaConvert provides this data through events that it sends to EventBridge\. You can subscribe to these events to receive job notifications programmatically or through Amazon SNS\.  
For more information about using events, see [Using EventBridge with AWS Elemental MediaConvert](eventbridge_events.md)\.

**Topics**
+ [Using EventBridge with AWS Elemental MediaConvert](eventbridge_events.md)
+ [Using CloudWatch with MediaConvert](cloudwatch_metrics.md)
+ [Logging MediaConvert API calls with AWS CloudTrail](logging-using-cloudtrail.md)