# Working with AWS Elemental MediaConvert jobs<a name="working-with-jobs"></a>

A job does the work of transcoding a media file\. When you create a job, you specify the information that MediaConvert requires to perform the transcoding\. For example, you specify which files to transcode, what to name the transcoded files and where to save them, which advanced features to apply, and so on\.

You can work with your jobs in the following ways:
+ **Create job** – When you create a job, you simultaneously submit it to a queue for processing\. Processing begins automatically from your queues as resources allow\. For information about resource allocation, see [How MediaConvert allocates >resources and prioritizes jobs >with on\-demand queues](about-on-demand-queues.md#about-resource-allocation-and-job-prioritization)\.     
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/working-with-jobs.html)
+ **View jobs history** – You can view a record of any job that you've created within the last three months\. This record shows the job settings and the job's completion status \(SUBMITTED, PROGRESSING, COMPLETE, or ERROR\)\. After a job record is three months old, MediaConvert automatically deletes it\.

  For instructions about listing and viewing your job history, see [Viewing your job history](viewing-job-history.md)\.
+ **Cancel job** – You can cancel a job anytime after you submit it and before the service uploads the job outputs to your output Amazon S3 bucket\.

  For instructions about canceling a job, see [Canceling a job](canceling-a-job.md)\.