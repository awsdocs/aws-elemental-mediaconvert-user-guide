# Events that AWS Elemental MediaConvert sends to CloudWatch<a name="mediaconvert_cwe_events"></a>

AWS Elemental MediaConvert sends change events about the status of jobs to CloudWatch Events\. You can create CloudWatch Events rules for any of the following events\.


| Event | Sent when | Contains | 
| --- | --- | --- | 
|  `PROGRESSING`  |  A job moves from the `SUBMITTED` state to the `PROGRESSING` state\.   |  Time in queue\.   | 
| STATUS\_UPDATE |  Approximately one minute has elapsed since MediaConvert began processing the job\. By default, updates are sent approximately every minute after that, until the service finishes transcoding or encounters an error\. You can optionally specify a different update frequency in your job, with the **Status update interval** setting\. For more frequent updates than the default, you can choose 10, 12, 15, 20, or 30 seconds\. For less frequent updates than the default, you can choose anywhere from 2 to 10 minutes, in increments of one minute\.  |  The phase your job is in, and, when available, job and phase percent completion\. Job phases are as follows: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/mediaconvert_cwe_events.html)  | 
|  `COMPLETE`  |  A job completes successfully\. MediaConvert generated all outputs without errors\.  |  Warnings and output information about the completed job\.  | 
|  `ERROR`  |  A job has an error\. At least one output has an error\.  |  The error code or codes and any messages, as well as warnings or any other ephemeral job information about the job's error status\.   | 
|  NEW\_WARNING  |  A warning condition arises\. Warning conditions don't stop the job from running\.  |  The submission queue ARN, the job ID, and a warning message\. Warning messages inform you about conditions that don't stop the job but may indicate that the job is not progressing as you planned\. For example, a job that you set up to hop queues reaches the wait time you specified, but can't hop\. Note that NEW\_WARNING reports only the most recent warning message; it doesn't report previous warnings, even if those warning conditions are still in effect\.  | 
|  `INPUT_INFORMATION`  |  Soon after MediaConvert begins processing the job\.  |  Media information, such as frame height and width, frame rate, and codec\.  MediaConvert includes information for all inputs in a single event\.  | 
| QUEUE\_HOP | A job hops queues\. | The ARNs for both queues and the job's priority within the queues\. | 

**Note**  
After a job has been in the `PROGRESSING` state for 48 hours, the service puts it into an `ERROR` state and stops working on it\. You are not billed for jobs that end in an `ERROR` state\.

## Adjusting the status update interval<a name="adjusting-the-status-update-interval"></a>

AWS Elemental MediaConvert sends STATUS\_UPDATE events to CloudWatch Events to let you know how your job is progressing\.

 By default, MediaConvert sends these events approximately once per minute\. You can optionally specify a different update frequency in your job\.

**To specify the STATUS\_UPDATE frequency**

1. On the **Create job** page, in the **Job** pane on the left, in the **Job settings** section, choose **Settings**\.

1. In the **Job settings** section on the right, for **Status update interval \(sec\)**, choose interval, in seconds, between updates\.

If you use the API or an SDK, you can find this setting in the JSON file of your job\. The setting name is [statusUpdateInterval](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-createjobrequest-statusupdateinterval)\.