# How queues work in AWS Elemental MediaConvert<a name="how-queues-work"></a>

For both on\-demand and reserved queues, AWS Elemental MediaConvert processes the jobs that you submit to a queue in parallel until the resources that are available to the queue are used\. When MediaConvert is using all the transcoding resources that are available to the queue, it holds any more jobs that you send to the queue without processing them\. When MediaConvert finishes one of the jobs that it's currently processing, it begins processing the next job in the queue\. MediaConvert determines the next job by the priority value that you assign when you create the job\.

The time that is required to complete a job varies significantly based on the size of the file that you're converting and the job specifications\. Accordingly, MediaConvert doesn't always finish jobs in the order that you create them\.

You can temporarily stop processing jobs by pausing the queue\. When you pause a queue, MediaConvert continues processing any jobs that it already started, but doesn't start any new jobs from that queue\. You can still submit jobs to a paused queue and cancel jobs in a paused queue\.

You must submit all jobs to a queue\. If you don't specify the queue when you create the jobs, AWS Elemental MediaConvert sends them to the default queue\. The default queue is an on\-demand queue\. You can have up to 10 on\-demand queues, including your default queue\.

**Topics**
+ [About on\-demand queues](about-on-demand-queues.md)
+ [About reserved queues](about-reserved-queues.md)
+ [Setting the priority of a job](setting-the-priority-of-a-job.md)
+ [Setting up queue hopping to avoid long waits](setting-up-queue-hopping-to-avoid-long-waits.md)