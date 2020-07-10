# Canceling an AWS Elemental MediaConvert job<a name="canceling-a-job"></a>

The following procedure explains how to cancel a job using the AWS Elemental MediaConvert console\. 

**To cancel a job**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar at the top of the page, choose the Region where you created the job that you want to cancel\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. **\(Optional but recommended\)** If your job has not yet started, pause the queue that contains the job so that the service doesn't start to process it\.

   1. Choose the three\-bar icon on the left to access the left navigation pane\.

   1.  Choose **Queues**\.

   1. Choose the name of the queue that you want to pause\.

   1. Choose **Edit queue**\.

   1. Under the **Status** dropdown list, choose **Pause**\.

1. In the left navigation pane of the console, choose **Jobs**\.

1. From the **Jobs** page, choose the job that you want to cancel by choosing the option \(![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/circle-icon.png)\) next to it\.

1. Choose the **Cancel job** button\.

1. If you paused the queue, make it active again so that it resumes processing jobs:

   1. In the left navigation pane, choose **Queues**\.

   1. Choose the name of the queue that you paused\.

   1. Under the **Status** dropdown list, choose **Active**\.