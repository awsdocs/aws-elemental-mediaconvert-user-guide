# Job history with queue hopping<a name="job-queue-hopping-history"></a>

**Viewing the settings values of hopped jobs**  
When a job hops queues, the values for the settings `queue` and `priority` remain how you set them when you created the job\. You can see the values for the job's post\-hop destination and queue priority in these ways:
+ In the console, you can see the values for the job's post\-hop destination queue and priority\. To see these settings, view the job details and then choose **Settings**\. For more information about viewing the details of your completed jobs, see [Viewing your job history](viewing-job-history.md)\.
+ When you send a `GetJob` request, you can see these values in the response body under `queueTransitions`\.

**Billing tags for hopped jobs**  
If you use tags on your MediaConvert queues to sort your AWS bill, the charges for your jobs are under the submission queue, not the execution queue\. For more information about using tags to sort your AWS bill, see [Setting up AWS Elemental MediaConvert resources for cost allocation through tagging](setting-up-resources-for-catt.md)\.

**Note**  
Cost allocation based on queue only applies to jobs executed in on\-demand queues\. When your submission queue is a reserved queue and your job hops to an on\-demand queue, the charges for that on\-demand job appear in your cost allocation report\. If you don't put tags on your reserved queue, those charges appear in the report unsorted\.

**Listing hopped jobs**  
When you call `ListJobs` or when you view your jobs on the console, if you filter by queue, MediaConvert shows you the jobs that you submitted to that queue\. For example, if you submit a job to `Queue1` and it hops to `Queue2`, that job appears in lists filtered for `Queue1` and not in lists filtered for `Queue2`\.