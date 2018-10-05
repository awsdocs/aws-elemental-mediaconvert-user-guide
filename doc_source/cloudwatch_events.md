# Using CloudWatch Events to Monitor AWS Elemental MediaConvert Jobs<a name="cloudwatch_events"></a>

You can use Amazon CloudWatch Events to notify you when your job status changes, to receive information about completed jobs, and to trigger automated actions in other AWS services when these events happen\. Here are some examples of what you can do with CloudWatch Events:
+ You can set up CloudWatch Events to notify you through email if one of your AWS Elemental MediaConvert jobs fails\. For a tutorial on setting up this CloudWatch Events event rule, see [Tutorial: Setting Up Email Notifications for Failed Jobs](mediaconvert_sns_tutorial.md)\.
+ You can use `COMPLETE` events to programmatically receive the file name and location of the job's outputs\. For more information, see [Output File Names and Paths](output-file-names-and-paths.md)\.
+ You can set up CloudWatch Events so that a Lambda function initiates your post\-processing code after your job finishes\. 

  For more information about using AWS Lambda with MediaConvert, see one of these resources:
  + For experienced cloud architects, see the [Video on Demand on AWS](https://aws.amazon.com/answers/media-entertainment/video-on-demand-on-aws/) post on the *AWS Answers* blog\.
  + For developers new to MediaConvert and Lambda, see the [Automating MediaConvert Jobs with Lambda](https://github.com/aws-samples/aws-media-services-simple-vod-workflow/blob/master/7-MediaConvertJobLambda/README.md) tutorial on GitHub\. This tutorial is part of the Simple VOD Workflow series of tutorials on using MediaConvert to create video on demand \(VOD\)\.

To set up CloudWatch Events, you create a rule that links MediaConvert and the service that responds to your job status change, such as Amazon Simple Notification Service \(SNS\) or AWS Lambda\. The following illustration shows these two parts of CloudWatch Events rules\. 

![\[CloudWatch Events rules bring together an event source and a target.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_overview.png)

For more information about the events that MediaConvert can send in the CloudWatch Events event stream, see [AWS Elemental MediaConvert Events](mediaconvert_cwe_events.md)\.