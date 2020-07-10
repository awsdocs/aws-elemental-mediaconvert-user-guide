# Monitoring AWS Elemental MediaConvert<a name="monitoring-overview"></a>

**Monitoring the Progress of Your AWS Elemental MediaConvert Jobs**  
You can track the status, phase, and percent completion of your jobs\. For information about status and phase, see [How AWS Elemental MediaConvert jobs progress](how-mediaconvert-jobs-progress.md)\.

You can monitor the status of your jobs and their percent completion in these places:
+ *AWS Elemental MediaConvert **Jobs** page*

  On the console, you can see your job status and the overall percent completion of your jobs\. For more granular information, such as percent completion of the probing, transcoding, and uploading phase, use Amazon CloudWatch Events, discussed in the following bullet\.

  Access the **Jobs** page by opening the [AWS Elemental MediaConvert console](https://console.aws.amazon.com/mediaconvert/) and choosing **Jobs** in the navigation pane\. If the navigation pane is closed, choose the menu icon \(the three\-bar icon\) in the upper\-left corner of the console to open it\.

  Optionally, you can filter to see only jobs that are progressing\. From the **Any status** filter, choose **Progressing**\.
+ *Amazon CloudWatch Events* 

  With CloudWatch Events, you can get more detailed information about the progress of your jobs, including percent completion of the probing, transcoding, and uploading phases\. AWS Elemental MediaConvert sends these `STATUS_UPDATE` events to the CloudWatch Events service\. You can subscribe to these events to receive job notifications programmatically or through Amazon SNS\.

  For more information about using the STATUS\_UPDATE event, see [Using CloudWatch Events with AWS Elemental MediaConvert](cloudwatch_events.md)\.

**Monitoring Your AWS Resources, Applications, and API Calls**  
The following AWS services help you stay on top of your resources and the activity on your account:
+ *Amazon CloudWatch* monitors your AWS resources and the applications that you run on AWS in real\-time\. You can collect and track metrics, create customized dashboards, and set alarms that notify you or that take actions when a specified metric reaches a threshold that you specify\. For example, you can have CloudWatch track the number of successful jobs over a specified period of time\. For more information, see the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\. For a list of the MediaConvert metrics that CloudWatch tracks, see [Using CloudWatch metrics to view metrics for AWS Elemental MediaConvert resources](MediaConvert-metrics.md)\.
+ *AWS CloudTrail* captures API calls and related events made by or on behalf of your AWS account and delivers the log files to an Amazon S3 bucket that you specify\. You can identify which users and accounts called AWS, the source IP address from which the calls were made, and when the calls occurred\. For more information, see [Logging MediaConvert API calls with AWS CloudTrail](logging-using-cloudtrail.md)\.

**Topics**
+ [How AWS Elemental MediaConvert jobs progress](how-mediaconvert-jobs-progress.md)
+ [Using CloudWatch Events with AWS Elemental MediaConvert](cloudwatch_events.md)
+ [Using CloudWatch metrics to view metrics for AWS Elemental MediaConvert resources](MediaConvert-metrics.md)