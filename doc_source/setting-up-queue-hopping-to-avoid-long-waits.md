# Setting up queue hopping to avoid long waits<a name="setting-up-queue-hopping-to-avoid-long-waits"></a>

You can set up your AWS Elemental MediaConvert job to automatically hop from the queue that you originally submit it to over to a different queue when the job waits too long\. The queue that you originally submit a job to is its *submission* queue\. The queue that a job goes to when it hops queues is the *destination* queue\. Regardless of whether a job hops queues, the queue that MediaConvert ultimately executes the job from is the *execution* queue\.

A common use case for queue hopping is to set up your jobs to usually go through your reserved queue, except when there is a spike in the use of that queue\. For example, you might want your jobs to go through your reserved queue whenever they can do so without waiting in the queue longer than 10 minutes\. In this case, you would submit your job to your reserved queue, specify an on\-demand queue as your hop destination queue, and set the wait time to 10 minutes\.

**Topics**
+ [Setting up queue hopping](setting-up-queue-hopping.md)
+ [Job history with queue hopping](job-queue-hopping-history.md)
+ [Job priority and queue hopping](job-priority-and-queue-hopping.md)
+ [Queue hopping behavior with paused queues](queue-hopping-with-paused-queues.md)