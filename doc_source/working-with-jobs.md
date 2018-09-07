# Working with AWS Elemental MediaConvert Jobs<a name="working-with-jobs"></a>

A job does the work of transcoding a media file\. When you create a job, you specify the information that MediaConvert requires to perform the transcoding\. For example, you specify which files to transcode, what to name the transcoded files and where to save them, which advanced features to apply, and so on\.

You can work with your jobs in the following ways:
+ **Create job** – When you create a job, you simultaneously submit it to a queue for processing\. Processing begins automatically from your queues as resources allow\. For information about resource allocation, see [How Jobs Are Prioritized](about-resource-allocation-and-job-prioritization.md)\.     
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/working-with-jobs.html)
+ **View jobs history** – You can view a record of any job that you've created within the last three months\. This record shows the job settings and the job's completion status \(SUBMITTED, PROGRESSING, COMPLETE, or ERROR\)\. After a job record is three months old, MediaConvert automatically deletes it\.

  For instructions about listing and viewing your job history, see [Viewing Your Job History](viewing-job-history.md)\.
+ **Cancel job** – You can cancel a job when its status is SUBMITTED, which is when it's in a queue, but before the service begins transcoding it\. After the service begins transcoding a job, you can't cancel or delete it\.

  For instructions about canceling a job, see [Canceling a Job](canceling-a-job.md)\.