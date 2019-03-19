# Monitoring AWS Elemental MediaConvert Jobs<a name="monitoring-overview"></a>

You can keep on top of your AWS Elemental MediaConvert jobs in these ways:
+ *Amazon CloudWatch Events* delivers a near real\-time stream of system events that describe changes in AWS resources\. Some examples of what you can do with AWS Elemental MediaConvert CloudWatch Events are as follows:
  + You can monitor the progress of your job with `STATUS_UPDATE` event notifications\. 

    For more information, see `STATUS_UPDATE` in the table of event types in [AWS Elemental MediaConvert Events](mediaconvert_cwe_events.md)\.
  + You can set up notifications for your job status changes\. 

    For more information and a tutorial on setting up email job notifications with CloudWatch Events, see [Using CloudWatch Events to Monitor AWS Elemental MediaConvert Jobs](cloudwatch_events.md)\.
  + You can get details about your job outputs\.

    AWS Elemental MediaConvert provides details about your job outputs in the notification for the `COMPLETE` event\. This information includes the location and file names of the job's media files and manifests\. For details, see [Output File Names and Paths](output-file-names-and-paths.md)\.
  + You can use trigger automated actions in other AWS services when your job status changes\.

    A common use case is to trigger a Lambda function to initiate your postprocessing\. For more information, see the *[Amazon CloudWatch Events User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/)*\.
+ *Amazon CloudWatch* monitors your AWS resources and the applications that you run on AWS in real\-time\. You can collect and track metrics, create customized dashboards, and set alarms that notify you or that take actions when a specified metric reaches a threshold that you specify\. For example, you can have CloudWatch track the number of successful jobs over a specified period of time\. For more information, see the *[Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)*\. For a list of the MediaConvert metrics that CloudWatch tracks, see [CloudWatch Metrics](MediaConvert-metrics.md)\.
+ *AWS CloudTrail* captures API calls and related events made by or on behalf of your AWS account and delivers the log files to an Amazon S3 bucket that you specify\. You can identify which users and accounts called AWS, the source IP address from which the calls were made, and when the calls occurred\. For more information, see [Logging MediaConvert API Calls with CloudTrail](logging-using-cloudtrail.md)\.
+ The *MediaConvert Recent Jobs* page shows the status of your jobs\. Access it by opening the MediaConvert console and choosing **Jobs** in the navigation pane\. You might need to choose the menu icon \(the three\-bar icon\) in the upper\-left corner of the console to open this navigation pane\.