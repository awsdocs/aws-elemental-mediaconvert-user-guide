# Working with AWS Elemental MediaConvert queues<a name="working-with-queues"></a>

AWS Elemental MediaConvert queues allow you to manage the resources that are available to your account for parallel processing of jobs\. MediaConvert offers two queue types: on\-demand and reserved queues\.

On\-demand queues  
With on\-demand queues, you don't have to set up anything in advance\. You send your jobs to an on\-demand queue whenever you want\. You pay per minute, billed in increments of \.01 minute\. Your default queue is an on\-demand queue\.

Reserved queues  
With reserved queues, you pay for the transcoding capacity of the entire queue, regardless of how much or how little you use it\. You make a 12\-month commitment, which AWS bills you for monthly\.

You can set up your job to automatically hop from its original queue to a fallback queue if the wait time in the original queue is too long\. For more information, see [Setting up queue hopping to avoid long waits](setting-up-queue-hopping-to-avoid-long-waits.md)\.

If you use Dolby audio encoding or audio normalization, AWS charges you per\-minute billing fees, regardless of which type of queue you use\.

The following topics provide more information about how queues work in general, and about each type of queue specifically\.

**Topics**
+ [How queues work](how-queues-work.md)
+ [Working with on\-demand queues](working-with-on-demand-queues.md)
+ [Working with reserved queues](working-with-reserved-queues.md)