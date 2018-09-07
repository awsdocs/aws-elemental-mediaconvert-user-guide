# Canceling an MediaConvert Job<a name="canceling-a-job"></a>

You can cancel any job in a queue that the service hasn't started to transcode\. 

**To cancel a job**

1. Sign in to the AWS Management Console and open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. On the navigation bar at the top of the page, choose the region where you created the job that you want to cancel\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. **\(Optional but recommended\)** Pause the queue that contains the job so that the service doesn't start to process it\. You can't cancel a job after the service starts processing it\.

   1. Choose the three\-bar icon on the left to access the left navigation pane\.

   1.  Choose **Queues**\.

   1. Choose the name of the queue that you want to pause\.

   1. Choose **Edit queue**\.

   1. Under the **Status** dropdown list, choose **Pause**\.

1. In the left navigation pane of the console, choose **Jobs**\.

1. In the **Recent jobs** pane, from the **Status** dropdown list, choose **Submitted** to filter your list of jobs to just those that you can cancel\.

   To view more details about a job to determine whether it's the one that you want to cancel, choose the job ID\.

1. From the **Recent jobs** pane, choose the job that you want to cancel by choosing the radio button next to it\.

1. Choose the **Cancel job** button\.

1. If you paused the queue, make it active again so that it resumes processing jobs:

   1. In the left navigation pane, choose **Queues**\.

   1. Choose the name of the queue that you paused\.

   1. Under the **Status** dropdown list, choose **Active**\.