# Using CloudWatch Events with AWS Elemental MediaConvert<a name="cloudwatch_events"></a>

You can use Amazon CloudWatch Events to monitor your AWS Elemental MediaConvert jobs\. Here are some examples of what you can do with CloudWatch Events:
+ **Monitor the progress of your job\.**

  `STATUS_UPDATE` events provide information about what phase your job is in \(`PROBING`, `TRANSCODING`, and `UPLOADING`\)\. For some jobs, AWS Elemental MediaConvert provides an estimate of how far your job has progressed, shown as a percentage of the total time from when your job leaves its queue to when your output files appear in your output Amazon S3 bucket\.

  For more information about `STATUS_UPDATE` events, see the table of event types in [Events that AWS Elemental MediaConvert sends to CloudWatch](mediaconvert_cwe_events.md)\.

  For information about adjusting the frequency of status updates, see [Adjusting the status update interval](mediaconvert_cwe_events.md#adjusting-the-status-update-interval)\.
+ **Set up email notifications for any failed jobs\.**

  For a tutorial on setting up this CloudWatch Events event rule, see [Tutorial: Setting up email notifications for failed jobs](mediaconvert_sns_tutorial.md)\.

  This is a specific example of setting up a CloudWatch Events event rule to find out about changes to your job status\. For a list of all job status change notifications that you can set up event rules for, see [Events that AWS Elemental MediaConvert sends to CloudWatch](mediaconvert_cwe_events.md)\.
+ **Get details about your job outputs\.**

  AWS Elemental MediaConvert provides details about your job outputs in the notification for the `COMPLETE` event\. This information includes the location and file names of the job's media files and manifests\. For details, see [Output file names and paths](output-file-names-and-paths.md)\.
+ **Automatically initiate post\-processing with an AWS Lambda function\.**

  You can set up CloudWatch Events so that a Lambda function initiates your post\-processing code after your job finishes\. For more information about using AWS Lambda with AWS Elemental MediaConvert, see one of these resources:
  + For experienced cloud architects, see the [Video on demand on AWS](https://aws.amazon.com/solutions/video-on-demand-on-aws/) post on the *AWS Answers* blog\.
  + For developers new to MediaConvert and Lambda, see the [Automating MediaConvert jobs with Lambda](https://github.com/aws-samples/aws-media-services-simple-vod-workflow/blob/master/7-MediaConvertJobLambda/README.md) tutorial on GitHub\. This tutorial is part of the Simple VOD Workflow series of tutorials on using MediaConvert to create video on demand \(VOD\)\.

**Topics**
+ [Setting up CloudWatch Events rules](setting-up-cloudwatch-event-rules.md)
+ [Tutorial: Setting up email notifications for failed jobs](mediaconvert_sns_tutorial.md)
+ [Output file names and paths](output-file-names-and-paths.md)
+ [Events that AWS Elemental MediaConvert sends to CloudWatch](mediaconvert_cwe_events.md)