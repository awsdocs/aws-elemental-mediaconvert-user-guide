# Monitoring MediaConvert job progress<a name="how-mediaconvert-jobs-progress"></a>

A job's *status* tells you, at the highest level, what is happening with your job\. Successful jobs go through the following statuses, in this order:

1. `SUBMITTED`: Your job status is `SUBMITTED` when you choose the **Create** button on the console or send a [CreateJob](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-http-methods) request through the API or an SDK\. 

1. `PROGRESSING`: Your job status is `PROGRESSING` when the service begins processing\. This status continues until all of your job outputs are saved to your output Amazon S3 bucket, or until the job ends in an error\.

1. `COMPLETE`: Your job status is `COMPLETE` when all of your job outputs are saved to your output Amazon S3 bucket\.

Unsuccessful jobs have an `ERROR` status\. When you cancel a job, its status becomes `CANCELED`\.

MediaConvert can emit an EventBridge event for the following job statuses: `INPUT_INFORMATION`, `PROGRESSING`, `STATUS_UPDATE`, `COMPLETE`, `ERROR`, `NEW_WARNING`, and `QUEUE_HOP`\. 

**Note**  
Most jobs will only emit a few of these events, with the most common being: `INPUT_INFORMATION`, `PROGRESSING`, and `COMPLETE`\.

For more information about MediaConvert and EventBridge, see: [Using EventBridge with AWS Elemental MediaConvert](eventbridge_events.md)\.

**Job Phase**  
A job's *phase* tells you at a finer level of detail what is happening while the job's status is `PROGRESSING`\. While a job is progressing, it goes through the following phases, in this order:

1. `PROBING`: When your job is in the `PROBING` phase, MediaConvert reads the information from your input files that the service needs for transcoding\.

1. `TRANSCODING`: When your job is in the `TRANSCODING` phase, the service demuxes, decodes, encodes, and remuxes your content\. In some jobs, the service begins uploading outputs to your output Amazon S3 bucket during this phase\. The phase ends when all transcoding is complete\.

1. `UPLOADING`: When your job is in the `UPLOADING` phase, the service uploads your transcoded outputs to your output Amazon S3 bucket\. In the case of outputs that the service begins to upload during the `TRANSCODING` phase, the `UPLOADING` phase begins when the transcoding is done\. It continues until all uploads are finished\.