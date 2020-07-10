# About on\-demand queues<a name="about-on-demand-queues"></a>

On\-demand queues differ from reserved queues in how AWS Elemental MediaConvert allocates transcoding resources for jobs and in how you pay for your transcoded outputs\.

## How MediaConvert allocates resources and prioritizes jobs with on\-demand queues<a name="about-resource-allocation-and-job-prioritization"></a>

There are two ways that you can affect how quickly MediaConvert processes a job that you send to an on\-demand queue: the priority that you set in the job's settings and the number of on\-demand queues that you set up to process jobs in parallel\.

**Job Priority**  
Within a queue, MediaConvert processes jobs in parallel until all the resources available to the queue are used\. When a job finishes and resources are again available in the queue, MediaConvert selects the next job to process based on the job's priority\. If more than one job has the highest priority, MediaConvert begins the one that you submitted first\. 

You set the priority of a job when you create it\. For more information, see [Setting the priority of a job](setting-the-priority-of-a-job.md)\.

**Using multiple on\-demand queues**  
You might want to isolate the resource consumption of some of your jobs from the others\. For example, you might run different jobs for different customers\. You can isolate resources by creating additional on\-demand queues\. MediaConvert processes jobs across multiple queues in parallel\.

MediaConvert divides the processing capacity available to your account evenly among your on\-demand queues\. For example, if you have 10 videos that you want to transcode, the transcoding takes the same amount of time if you send them all to the default queue or if you create an additional on\-demand queue and send five jobs to each queue, assuming that the videos are of equal length and the transcoding jobs are of equal complexity\.

**Important**  
Creating additional queues doesn't increase the transcoding resources that are available to the account\. For example, when you create a second queue, you cut in half the resources that are available to your default queue\. This is true even when your additional queues are paused\.

## How you pay for transcoding with on\-demand queues<a name="how-you-pay-for-on-demand-queues"></a>

With on\-demand queues, you pay based on what you use\. After a job from your on\-demand queue successfully finishes, AWS bills you based on the duration of your outputs\. You pay a price per minute of output video, billed at \.01 minute increments\. The price per minute varies depending on your job configuration and the AWS Region that you choose for transcoding\. For pricing details, see [AWS Elemental MediaConvert pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

### Pricing tiers per output<a name="pricing-per-output"></a>

If you configure your job with multiple outputs, you pay for each output\. AWS bills you for the duration of the finished assets, not the transcoding time\.

Whether AWS bills you for an output at professional tier rates or basic tier rates depends on your job settings\. If you enable a job\-wide pro\-tier setting, such as accelerated transcoding, all of your outputs are billed at pro\-tier rates\. If you don't use any job\-wide pro\-tier features, each output is assessed for billing tier separately\.

For example, say that you don't enable job\-wide pro\-tier features and your input video file is 10 minutes, 30 seconds long \(10\.5 minutes\)\. You set up your job to create three outputs: 
+ One low\-resolution SD output encoded with AVC, billed at $0\.0075 per minute
+ One high\-resolution HD output using pro\-tier features at $0\.0630 per minute
+ One audio\-only output at $0\.005 per minute

You pay \($0\.0075 x 10\.5\) \+ \($0\.0630 x 10\.5\) \+ \($0\.005 x 10\.5\) = $0\.79275\.

Say that you run the same job as in the previous example, but you also enable accelerated transcoding\. Then your SD AVC output is billed at the pro\-tier pricing for AVC outputs\. In this case, you pay \($0\.024 x 10\.5\) \+ \($0\.0630 x 10\.5\) \+ \($0\.005 x 10\.5\) = $0\.966\.

These rates are examples only; for actual pricing rates, see the [AWS Elemental MediaConvert pricing](https://aws.amazon.com/mediaconvert/pricing/) page\.