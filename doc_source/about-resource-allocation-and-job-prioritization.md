# How AWS Elemental MediaConvert Allocates Resources and Prioritizes Jobs<a name="about-resource-allocation-and-job-prioritization"></a>

Queues allow you to manage the resources that are available to your AWS account for parallel processing of jobs\. AWS Elemental MediaConvert processes all jobs that are submitted to a queue in parallel until the service is using all the resources that are available to that queue\. After that, AWS Elemental MediaConvert begins processing the next job in the queue after it finishes one of the jobs that it's currently processing\.

If you have jobs of differing priorities, you can handle high\-priority jobs by creating a different queue from the default queue\. This distributes the resources that are available to the account across the two queues\. Because jobs across multiple queues are processed in parallel \(until the resources that are available to the account are used\), you can submit most jobs into the default queue and use the other queue only when you need to transcode a job immediately\. 

**Important**  
Creating additional queues does not increase the resources that are available to the account\. When you create a second queue, you are reserving resources that are therefore not available to your default queue\.

If you don't specify the queue when you create a job, AWS Elemental MediaConvert sends it to a default queue and starts them in the order in which you create them\. If you configure a job to create multiple outputs, for example in both DASH and HLS formats, AWS Elemental MediaConvert creates the files for each output in the order you specify them in the job\. 

**Note**  
The time that is required to complete a job varies significantly based on the size of the file that you're converting and the job specifications\. Accordingly, AWS Elemental MediaConvert doesn't always finish jobs in the order that you create them\. 

You can temporarily stop processing jobs by pausing the queue\. When you pause a queue, AWS Elemental MediaConvert continues processing any jobs that it has already started, but doesn't start any new jobs from that queue\. You can still submit jobs to a paused queue\. You can also cancel jobs in a paused queue that the service hasn't started processing\.