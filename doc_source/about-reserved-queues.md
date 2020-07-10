# About reserved queues in AWS Elemental MediaConvert<a name="about-reserved-queues"></a>

Reserved queues differ from on\-demand queues in how AWS Elemental MediaConvert allocates transcoding resources for jobs and in how you pay for your transcoding\.

**Note**  
There are a few features that you can't use with jobs that you send to a reserved queue\. For more information, see [Feature limitations with reserved queues](feature-limitations-with-reserved-queues.md)\.

## How MediaConvert allocates resources and prioritizes jobs with reserved queues<a name="resource-allocation-and-job-prioritization-with-reserved-queues"></a>

When you set up your reserved queue, you choose how many jobs it can run at once by specifying the number of reserved transcode slots \(RTS\) in the queue\. For example, if you send five jobs to a reserved queue with two RTS, AWS Elemental MediaConvert immediately begins processing the first two jobs that you submit and holds the other three in the queue\. When one of the jobs that MediaConvert is processing finishes, the service begins processing the next job\.

Each RTS has its own dedicated computing resources\. Therefore, when MediaConvert begins to process a job that you send to a reserved queue, it processes just as quickly if you have one RTS or multiple RTS\.

When a job in a reserved queue finishes, MediaConvert selects the next job to process based on the job's priority\. You set the priority of a job when you create it\. If more than one job has the highest priority, MediaConvert begins the one that you submitted first\. For more information, see [Setting the priority of a job](setting-the-priority-of-a-job.md)\.

## How you pay for transcoding with reserved queues<a name="how-you-pay-for-reserved-queues"></a>

With reserved queues, you pay for the capacity in the queue regardless of whether you use it\. When you set up a reserved queue, you make a 12\-month commitment to a pricing plan\. The pricing plan specifies a fixed number of reserved transcode slots \(RTS\)\. AWS bills you monthly for your RTS\.

**Important**  
After you purchase your RTS, you can't cancel your 12\-month commitment\.

You can purchase additional capacity for a reserved queue that already has RTS\. To purchase additional capacity, you extend your existing commitment with a new 12\-month commitment for a larger number of RTS\. The new commitment begins when you purchase the additional capacity\. You can't decrease the number of RTS in your reserved queue\.

When your pricing plan term expires, your reserved queue persists\. You can still send jobs to it, but AWS Elemental MediaConvert doesn't run them\.

**About Auto Renew**  
You can set your pricing plan to auto renew\. When your pricing plan term ends, AWS Elemental MediaConvert checks the auto renew status\. If auto renew is enabled at that time, you automatically commit to another 12\-month term for the same number of RTS at the same price\. You can change the auto renew status at any time\.

You can choose auto renew when you set up your queue\. Anytime after that, you can change the auto renew status on the **Edit** page for the queue\. For more information, see [Creating a reserved queue](creating-a-reserved-queue.md) and [Editing reserved queues](editing-reserved-queues.md)\.