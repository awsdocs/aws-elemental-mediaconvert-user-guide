# About On\-Demand Queues<a name="about-on-demand-queues"></a>

On\-demand queues differ from reserved queues in how AWS Elemental MediaConvert allocates transcoding resources for jobs and in how you pay for your transcoded outputs\.

## How MediaConvert Allocates Resources and Prioritizes Jobs with On\-Demand Queues<a name="about-resource-allocation-and-job-prioritization"></a>

There are two ways that you can affect how quickly MediaConvert processes a job that you send to an on\-demand queue: the priority that you set in the job's settings and the number of on\-demand queues that you set up to process jobs in parallel\.

**Job Priority**  
Within a queue, MediaConvert processes jobs in parallel until all the resources available to the queue are used\. When a job finishes and resources are again available in the queue, MediaConvert selects the next job to process based on the job's priority\. If more than one job has the highest priority, MediaConvert begins the one that you submitted first\. 

You set the priority of a job when you create it\. For more information, see [Setting the Priority of a Job](setting-the-priority-of-a-job.md)\.

**Using Multiple On\-Demand Queues**  
You might want to isolate the resource consumption of some of your jobs from the others\. For example, you might run different jobs for different customers\. You can isolate resources by creating additional on\-demand queues\. MediaConvert processes jobs across multiple queues in parallel\.

MediaConvert divides the processing capacity available to your account evenly among your on\-demand queues\. For example, if you have 10 videos that you want to transcode, the transcoding takes the same amount of time if you send them all to the default queue or if you create an additional on\-demand queue and send five jobs to each queue, assuming that the videos are of equal length and the transcoding jobs are of equal complexity\.

**Important**  
Creating additional queues doesn't increase the transcoding resources that are available to the account\. For example, when you create a second queue, you cut in half the resources that are available to your default queue\. This is true even when your additional queues are paused\.

## How You Pay for Transcoding with On\-Demand Queues<a name="how-you-pay-for-on-demand-queues"></a>

With on\-demand queues, you pay based on what you use\. After a job from your on\-demand queue successfully finishes, AWS bills you based on the duration of your outputs\. You pay a price per minute, billed at \.01 minute increments\. The price per minute varies depending on your job configuration and the AWS Region that you choose for transcoding\. For pricing details, see [AWS Elemental MediaConvert Pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

**Note**  
If you configure your job with multiple outputs, you pay for each output\. AWS bills you for the duration of the finished assets, not the transcoding time\.  
For example, your input video file is 10 minutes, 30 seconds long \(10\.5 minutes\) and you set up your job to create three outputs: one low\-resolution SD output at $0\.0075 per minute, one high\-resolution HD output using [pro\-tier features](https://aws.amazon.com/mediaconvert/pricing/) at $0\.0630 per minute, and one audio\-only output at $0\.0003 per minute\. You pay \($0\.0075 x 10\.5\) \+ \($0\.0630 x 10\.5\) \+ \($0\.0003 x 10\.5\) = $0\.7434\.