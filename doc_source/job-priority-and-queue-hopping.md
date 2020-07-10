# Job priority and queue hopping<a name="job-priority-and-queue-hopping"></a>

When you set up a job for queue hopping, you can optionally specify the priority for the job in the new queue\. If you don't specify a new priority, the job keeps the priority number from its submission queue\. If you use different guidelines for choosing the values for `priority` between the two queues, make sure to specify a new priority value for the job in the destination queue\.

For example, say that in your submission queue you use a value of 20 for urgent jobs, 10 for ordinary jobs, and 0 for low\-priority jobs\. And say that in your destination queue, you use a value of 10 for urgent jobs, 0 for ordinary jobs, and \-10 for low\-priority jobs\. When an ordinary job with a priority of 10 hops from your submission queue to the destination queue, it is scheduled with the destination queue's urgent jobs if you don't provide a new priority value\.

For information about setting the job's priority within the submission queue, see [Setting the priority of a job](setting-the-priority-of-a-job.md)\.

In the console, set the priority of the job within the destination queue with the setting **Queue hopping**, **Job priority**\. For details about finding this setting, see the procedure in the topic [Setting up queue hopping](setting-up-queue-hopping.md)\.

Set the priority of the job within the destination queue directly in your JSON job specification with the field `priority`, under `hopDestinations`\. 