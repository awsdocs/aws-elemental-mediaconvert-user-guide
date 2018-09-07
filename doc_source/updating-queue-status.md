# Pausing and Reactivating Queues in MediaConvert<a name="updating-queue-status"></a>

If you want to cancel a job, we recommend that you first pause the corresponding queue so that MediaConvert doesn't start processing the job\. After the status of a job changes from **Submitted** to **Progressing**, you can't cancel it\.

The following procedure explains how to pause and reactivate a queue using the console\.

**To pause or reactivate a queue**

1. Sign in to the AWS Management Console and open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. If you are pausing or reactivating a queue other than the default queue, on the navigation bar of the MediaConvert console, choose the region where the queue was created\.

   A default queue is available in all regions\. Other queues appear only in the region where they are created\.  
![\[Choose a region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. Choose the name of the queue that you want to pause or reactivate\.

1. On the queue’s page, choose the **Edit queue** button\.

1. On the **Edit queue** page, choose **Paused** or **Active**\.

1. Choose **Save queue**\.