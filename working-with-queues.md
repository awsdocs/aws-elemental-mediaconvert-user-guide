# Working with Queues<a name="working-with-queues"></a>

You can use queues to manage the resources that are available to your account for parallel processing of jobs\. When you create a job, you specify the queue that you want to add the job to\. If you don't specify a queue, AWS Elemental MediaConvert puts your job in the default queue\. AWS Elemental MediaConvert starts processing the jobs in a queue in the order in which you add them\. 

One common configuration is to use two queues: the default for standard\-priority jobs and a dedicated queue for high\-priority jobs\. Most jobs go into the default queue\. You use the high\-priority queue only when you need to transcode a file immediately\. 

If there are other jobs in a queue when you create a job, AWS Elemental MediaConvert starts processing the new job when resources are available\. A queue can process more than one job simultaneously\. The time required to complete a job varies significantly based on the size of the file you're converting and the job specifications\. As a result, jobs don't necessarily complete in the order in which you create them\. You can temporarily pause a queue so that it stops processing jobs\. This is useful if you want to cancel one or more jobs, which you can do only before AWS Elemental MediaConvert begins processing the jobs\. 


+ [Creating a Queue in AWS Elemental MediaConvert](creating-queues.md)
+ [Pausing and Reactivating Queues in AWS Elemental MediaConvert](updating-queue-status.md)
+ [Listing and Viewing Queues in AWS Elemental MediaConvert](listing-queues.md)
+ [Deleting an AWS Elemental MediaConvert Queue](deleting-a-queue.md)