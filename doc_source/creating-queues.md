# Creating an on\-demand queue in AWS Elemental MediaConvert<a name="creating-queues"></a>

AWS Elemental MediaConvert provides a default queue, which is an on\-demand queue\. But you can choose to create your own on\-demand queues to manage the resources that are available to your account\. For information about how queues affect the way that MediaConvert allocates the processing of resources, see [How MediaConvert allocates >resources and prioritizes jobs >with on\-demand queues](about-on-demand-queues.md#about-resource-allocation-and-job-prioritization)\.

**To create an on\-demand queue**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\. 

1. On the navigation bar of the AWS Elemental MediaConvert console, choose the Region where you want to create the queue\.

   A default queue is available in all Regions\. Other queues appear only in the Region where they are created\.  
![\[Choose a Region.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/regions-list.png)

1. Choose the three\-bar icon on the left to access the left navigation pane\.

1. Choose **Queues**\.

1. On the **Queues** page, in the **On\-demand queues** section, choose **Create queue**\.

1. Enter a name and a description for the new queue\.

1. Choose **Create queue**\.