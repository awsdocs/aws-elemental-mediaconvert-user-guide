# How Queues Work in AWS Elemental MediaConvert<a name="how-queues-work"></a>

For both on\-demand and reserved queues, AWS Elemental MediaConvert processes the jobs that you submit to a queue in parallel until the resources that are available to the queue are used\. When MediaConvert is using all the transcoding resources that are available to the queue, it holds any more jobs that you send to the queue without processing them\. When MediaConvert finishes one of the jobs that it's currently processing, it begins processing the first job waiting in the queue\.

**Note**  
The time that is required to complete a job varies significantly based on the size of the file that you're converting and the job specifications\. Accordingly, AWS Elemental MediaConvert doesn't always finish jobs in the order that you create them\.  
If you configure a job to transcode into more than one format, MediaConvert creates the files for each format in the same order that you specify the formats in the job\.

You can temporarily stop processing jobs by pausing the queue\. When you pause a queue, AWS Elemental MediaConvert continues processing any jobs that it has already started, but doesn't start any new jobs from that queue\. You can still submit jobs to a paused queue and cancel jobs in a paused queue\.

You must submit all jobs to a queue\. If you don't specify the queue when you create the jobs, AWS Elemental MediaConvert sends them to the default queue and starts them in the order in which you create them\. The default queue is an on\-demand queue\. You can create up to 10 total queues\.

## About On\-Demand Queues<a name="about-on-demand-queues"></a>

On\-demand queues differ from reserved queues in how AWS Elemental MediaConvert allocates transcoding resources for jobs and in how you pay for your transcodes\.

### Resource Allocation and Job Prioritization with On\-Demand Queues<a name="about-resource-allocation-and-job-prioritization"></a>

AWS Elemental MediaConvert divides the processing capacity available to your account evenly among your on\-demand queues\. For example, if you have 10 videos that you want to transcode, the transcoding takes the same amount of time if you send them all to the default queue or if you create an additional on\-demand queue and send five jobs to each queue, assuming that the videos are of equal length and the transcoding jobs are of equal complexity\.

If you have jobs of differing priorities, you can handle high\-priority jobs by creating a separate on\-demand queue from the default queue\. This distributes the resources that are available to the account across the two queues\. Because jobs across multiple queues are processed in parallel \(until the resources that are available to the account are used\), you can submit most jobs into the default queue and use the other queue only when you need to transcode a job immediately\.

**Important**  
Creating additional queues does not increase the transcoding resources that are available to the account\. When you create a second queue, you reserve resources that therefore are not available to your default queue\.

### How You Pay for Transcoding with On\-Demand Queues<a name="how-you-pay-for-on-demand-queues"></a>

With on\-demand queues, you pay based on what you use\. When you send a job to an on\-demand queue, and after the job successfully completes, AWS bills you based on the duration of your outputs\. You pay a price per minute, billed at \.01 minute increments\. The price per minute varies depending on your job configuration and the AWS Region that you choose for transcoding\. For pricing details, see [AWS Elemental MediaConvert Pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

**Note**  
If you configure your job with multiple outputs, you pay for each output\. AWS bills you for the duration of the finished assets, not the transcoding time\.  
For example, your input video file is 10 minutes, 30 seconds long \(10\.5 minutes\) and you set up your job to create three outputs: one low\-resolution SD output at $0\.0075 per minute, one high\-resolution HD output using [pro\-tier features](https://aws.amazon.com/mediaconvert/pricing/) at $0\.0630 per minute, and one audio\-only output at $0\.0003 per minute\. You pay \($0\.0075 x 10\.5\) \+ \($0\.0630 x 10\.5\) \+ \($0\.0003 x 10\.5\) = $0\.7434\.

## About Reserved Queues in AWS Elemental MediaConvert<a name="about-reserved-queues"></a>

Reserved queues differ from on\-demand queues in how AWS Elemental MediaConvert allocates transcoding resources for jobs and in how you pay for your transcoding\.

### Resource Allocation and Job Prioritization with Reserved Queues<a name="resource-allocation-and-job-prioritization-with-reserved-queues"></a>

When you set up your reserved queue, you choose how many jobs it can run at once by specifying the number of reserved transcode slots \(RTS\) in the queue\. For example, if you send five jobs to a reserved queue with two RTS, AWS Elemental MediaConvert immediately begins processing the first two jobs that you submit and holds the other three in the queue\. When one of the jobs that MediaConvert is processing finishes, the service begins processing the first job in the queue\.

### How You Pay for Transcoding with Reserved Queues<a name="how-you-pay-for-reserved-queues"></a>

With reserved queues, you pay for the capacity in the queue regardless of whether you use it\. When you set up a reserved queue, you make a 12\-month commitment to a pricing plan\. The pricing plan specifies a fixed number of reserved transcode slots \(RTS\)\. AWS bills you monthly for your RTS\.

**Important**  
After you purchase your RTS, you can't cancel your 12\-month commitment\.

You can purchase additional capacity for a reserved queue that already has RTS\. To purchase additional capacity, you extend your existing commitment with a new 12\-month commitment for a larger number of RTS\. The new commitment begins when you purchase the additional capacity\. You can't decrease the number of RTS in your reserved queue\.

When your pricing plan term expires, your reserved queue persists\. You can still send jobs to it, but AWS Elemental MediaConvert doesn't run them\.

**About Auto Renew**  
You can set your pricing plan to auto renew\. When your pricing plan term ends, AWS Elemental MediaConvert checks the auto renew status\. If auto renew is enabled at that time, you automatically commit to another 12\-month term for the same number of RTS at the same price\. You can change the auto renew status at any time\.

You can choose auto renew when you set up your queue\. Any time after that, you can change the auto renew status on the **Edit** page for the queue\. For more information, see [Creating a Reserved Queue](creating-a-reserved-queue.md) and [Editing Reserved Queues](editing-reserved-queues.md)\.