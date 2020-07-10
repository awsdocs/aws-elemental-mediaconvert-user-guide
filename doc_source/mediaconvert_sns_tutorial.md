# Tutorial: Setting up email notifications for failed jobs<a name="mediaconvert_sns_tutorial"></a>

In this tutorial, you configure a CloudWatch Events event rule that captures events when a job status changes to `ERROR` and then notifies you about the event\. To do this, you first create a topic in Amazon SNS that will send you an email notification about the failed job\. Next, you create a rule in CloudWatch Events by defining an event source and referencing the Amazon SNS topic \(the "target"\), as shown in the following illustration\.

![\[This CloudWatch Events rule brings together a job event that has an error and an Amazon SNS topic. The CloudWatch Events rule is represented by a rectangle that reads "Rule: Send me an email when one of my jobs has an error." Inside that rectangle are two rectangles, one representing the target and one representing the event source. The target rectangle reads "Target, Amazon SNS Topic: Use my SNS topic that sends an email to the address I provide." The event source rectangle reads "Event Source: AWS Elemental MediaConvert says one of my jobs has an error."\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/CloudWatchEvents_example.png)

**Topics**
+ [Prerequisites](mediaconvert_sns_prereq.md)
+ [Step 1: Create a topic in Amazon SNS](mediaconvert_sns_create_topic.md)
+ [Step 2: Specify an event source in a CloudWatch Events rule](mediaconvert_sns_rule_event_sourece.md)
+ [Step 3: Add the Amazon SNS topic and finish your rule](add-target-and-finish-rule.md)
+ [Step 4: Test your rule](mediaconvert_sns_test_rule.md)