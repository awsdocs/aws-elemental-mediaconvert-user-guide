# Setting Up CloudWatch Event Rules<a name="setting-up-cloudwatch-event-rules"></a>

To set up CloudWatch event rules, you create a rule that links AWS Elemental MediaConvert and the service that responds to your job status change, such as Amazon Simple Notification Service \(SNS\) or AWS Lambda\. The following illustration shows these two parts of CloudWatch Events rules\. 

![\[CloudWatch Events rules bring together an event source and a target.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_overview.png)

For a tutorial on setting up a CloudWatch rule with AWS Elemental MediaConvert, see [Tutorial: Setting Up Email Notifications for Failed Jobs](mediaconvert_sns_tutorial.md)\.

For a list of the events that MediaConvert sends in the CloudWatch Events event stream, see [Events That AWS Elemental MediaConvert Sends to CloudWatch](mediaconvert_cwe_events.md)\.

For more general information about using CloudWatch Events, see the [Amazon CloudWatch Events User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/)\.