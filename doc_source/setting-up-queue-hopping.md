# Setting up queue hopping<a name="setting-up-queue-hopping"></a>

When you set up queue hopping, you specify the *submission queue*, the *wait time*, and the *destination queue*\. The submission queue is the queue you want the job to go through, assuming that the wait in that queue isn't long\. The wait time is the length of time, in minutes, that the job will wait in the submission queue in the SUBMITTED state before hopping over to the destination queue\. The destination queue is the queue that the job moves to when it hops queues\. In the most common use case, the submission queue is a reserved queue and the destination queue is an on\-demand queue\.

**To set up queue hopping \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

1. In the **Job settings** section on the right, choose **Queue hopping**\.

1. For **Wait minutes**, enter the time, in whole minutes, that you want the job to wait in the submission queue before hopping\. You can enter a number from 1 through 1,440\.

1. For **Destination queue**, choose the queue that you want your job to hop to if it stays in the submission queue longer than the time you specify for **Wait minutes**\.

1. Optional\. For **Job priority**, specify the priority for the job within the destination queue\. For more information, see [Job priority and queue hopping](job-priority-and-queue-hopping.md)\.

   This **Job priority** value applies only when a job hops queues\. Jobs that are executed from their submission queue use the job priority value that you set in the usual way\. For more information, see [Setting the priority of a job](setting-the-priority-of-a-job.md)\.

**To set up queue hopping \(API, SDK, and AWS CLI\)**

1. Set up your JSON job specification\. Either manually edit your JSON file, or use the console to generate it as follows:

   1. Follow the previous procedure for the console\.

   1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

   In the MediaConvert job schema, you can find the settings for queueHopping under `hopDestinations`\.

1. Submit your job according to the instructions in the *AWS Elemental MediaConvert API Reference*:
   + If you're using one of the AWS SDKs or the AWS CLI, see [Getting started with MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)\.
   + If you're calling the MediaConvert API directly, see [Getting started with MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)\.