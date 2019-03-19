# AWS Elemental MediaConvert Events<a name="mediaconvert_cwe_events"></a>

AWS Elemental MediaConvert sends change events about the status of jobs to CloudWatch Events\. You can create CloudWatch Events rules for any of the following events\.


**Job Status Change Events**  

| Event | Sent When | Contains | 
| --- | --- | --- | 
|  `PROGRESSING`  |  A job moves from the `SUBMITTED` state to the `PROGRESSING` state\.   |  Time in queue\.   | 
| STATUS\_UPDATE |   Approximately one minute has elapsed since MediaConvert began processing the job\. By default, updates are sent approximately every minute after that, until the service completes the transcode or encounters an error\.  You can optionally specify a different update frequency in your job, with the **Status update interval** setting\. For more frequent updates than the default, you can choose 10, 12, 15, 20, or 30 seconds\. For less frequent updates than the default, you can choose anywhere from 2 to 10 minutes, in increments of one minute\.   |   The phase your job is in, and, when available, job percent completion\. Job phases are as folllows:    [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/mediaconvert_cwe_events.html)     | 
|  `COMPLETE`  |  A job completes successfully\. MediaConvert generated all outputs without errors\.  |  Warnings and output information about the completed job\.  | 
|  `ERROR`  |  A job has an error\. At least one output has an error\.  |  The error code or codes and any messages, as well as warnings or any other ephemeral job information about the job's error status\.   | 
|  `INPUT_INFORMATION`  |  Soon after MediaConvert begins processing the job\.  |  Media information, such as frame height and width, framerate, and codec\.  MediaConvert includes information for all inputs in a single event\.  | 