# Working with CloudWatch Events and AWS Elemental MediaConvert<a name="cloudwatch_events"></a>

You can use Amazon CloudWatch Events to notify you when your job status changes and to trigger automated actions in other AWS services when these events happen\. For example, you can set up CloudWatch Events to notify you if your AWS Elemental MediaConvert job fails\. You can also set up CloudWatch Events so that a Lambda function initiates your post\-processing code after your job finishes\.

To set up CloudWatch Events, you create a rule that links AWS Elemental MediaConvert and the service that responds to your job status change, such as Amazon Simple Notification Service \(SNS\) or AWS Lambda\. The following illustration shows these two parts of CloudWatch Events rules\. 

![\[CloudWatch Events rules bring together an event source and a target.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_overview.png)

For example, you can create a rule and name it "MediaConvert Job Error"\. Next, you can set up an Amazon SNS topic that has the email address that you want the notification sent to\. The event source is the event that AWS Elemental MediaConvert sends to CloudWatch when the status of a job changes to `ERROR`\. For a tutorial on setting up this CloudWatch Events event rule, see [[ERROR] BAD/MISSING LINK TEXT](mediaconvert_sns_tutorial.md)\.

For more information about the events that AWS Elemental MediaConvert can send in the CloudWatch Events event stream, see [[ERROR] BAD/MISSING LINK TEXT](mediaconvert_cwe_events.md)\.