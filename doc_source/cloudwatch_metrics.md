# Using CloudWatch with MediaConvert<a name="cloudwatch_metrics"></a>

You can use Amazon CloudWatch to gather metrics about your AWS Elemental MediaConvert jobs\. Here are some examples of what you can do with CloudWatch:

**Get details about your requests, queues, jobs, and outputs**  
Metrics are grouped according to dimension, including Operation metrics, Queue metrics, and Job metrics\.  
+ *Operation metrics* include any errors that occur when you interact with MediaConvert\.
+ *Queue metrics* include details about all of your jobs in a given queue, like the total number of jobs, or the total duration of your outputs\.
+ *Job metrics* include details about your outputs that you can use to identify trends, statistics, or potential issues with your video workflow\.
For more information, see [List of MediaConvert CloudWatch metrics](metrics.md)\.

**Create CloudWatch dashboards and alarms**  
You can create CloudWatch dashboards to track things for a job queue\. For example, you can track transcoding jobs that have completed or that have errors\. You can also use metrics such as `StandbyTime` to create alarms to detect if there is a large backlog for a job queue\. For more information, see [Creating dashboards and alarms for AWS Elemental MediaConvert using Amazon CloudWatch](http://aws.amazon.com/blogs/media/creating-dashboards-and-alarms-for-aws-elemental-mediaconvert-using-amazon-cloudwatch/)\.

**Topics**
+ [List of MediaConvert CloudWatch metrics](metrics.md)