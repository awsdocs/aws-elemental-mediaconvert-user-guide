# Using EventBridge with AWS Elemental MediaConvert<a name="eventbridge_events"></a>

You can use Amazon EventBridge to monitor your AWS Elemental MediaConvert jobs\. Here are some examples of what you can do with EventBridge:

**Get details about your job outputs**  
AWS Elemental MediaConvert provides details about your job outputs in the notification for the `COMPLETE` event\. This information includes the location and file names of the job's media files and manifests\. For details, see [Events with COMPLETE status](ev_status_complete.md)\.  
For information about job metrics sent to Amazon CloudWatch, see [Using CloudWatch with MediaConvert](cloudwatch_metrics.md)\.

**Set up email notifications for job status changes**  
To set up an EventBridge event rule, see [Tutorial: Setting up email notifications for failed jobs](setting-up-cloudwatch-event-rules.md#mediaconvert_sns_tutorial)\.  
For a list of all job status change notifications that you can set up event rules for, see [List of MediaConvert EventBridge events](mediaconvert_event_list.md)\.

**Monitor the progress of your job**  
`STATUS_UPDATE` events provide information about what phase your job is in \(`PROBING`, `TRANSCODING`, and `UPLOADING`\)\. For some jobs, MediaConvert provides an estimate of how far your job has progressed\. This estimate is shown as a percentage of the total time from when your job leaves its queue to when your output files appear in your output Amazon S3 bucket\.  
For more information about `STATUS_UPDATE` events, see the table of event types in [List of MediaConvert EventBridge events](mediaconvert_event_list.md)\.  
For information about adjusting the frequency of status updates, see [Adjust the status update interval](adjusting-the-status-update-interval.md)\.

**Automatically initiate post\-processing with an AWS Lambda function**  
You can set up EventBridge so that an AWS Lambda function initiates your post\-processing code after your job finishes\. For more information about using AWS Lambda with AWS Elemental MediaConvert, see one of these resources:  
+ For experienced cloud architects, see the [Video on demand on AWS](https://aws.amazon.com/solutions/video-on-demand-on-aws/) post on the *AWS Answers* blog\.
+ For developers new to MediaConvert and Lambda, see the [Automating MediaConvert jobs with Lambda](https://github.com/aws-samples/aws-media-services-simple-vod-workflow/blob/master/7-MediaConvertJobLambda/README.md) tutorial on GitHub\.

EventBridge delivers each event from the MediaConvert event stream at least once\.

MediaConvert does not require any additional permissions to deliver events to EventBridge\.

**Topics**
+ [Setting up EventBridge rules](setting-up-cloudwatch-event-rules.md)
+ [Monitoring MediaConvert job progress](how-mediaconvert-jobs-progress.md)
+ [List of MediaConvert EventBridge events](mediaconvert_event_list.md)