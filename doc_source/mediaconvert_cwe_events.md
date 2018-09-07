# MediaConvert Events<a name="mediaconvert_cwe_events"></a>

MediaConvert sends change events about the status of jobs to CloudWatch Events\. You can create CloudWatch Events rules for any of the following events\.


**Job Status Change Events**  

| Event | Sent When | Contains | 
| --- | --- | --- | 
|  `PROGRESSING`  |  A job moves from the `SUBMITTED` state to the `PROGRESSING` state\.   |  Time in queue\.   | 
| STATUS\_UPDATE | Approximately one minute has elapsed since MediaConvert began processing the job\. Sent approximately every minute after that, until the service completes the transcode or encounters an error\. | Job progress expressed in the number of frames transcoded since the beginning of the job\. | 
|  `COMPLETE`  |  A job completes successfully\. MediaConvert generated all outputs without errors\.  |  Warnings and output information about the completed job\.  | 
|  `ERROR`  |  A job has an error\. At least one output has an error\.  |  The error code or codes and any messages, as well as warnings or any other ephemeral job information about the job's error status\.   | 
|  `INPUT_INFORMATION`  |  Soon after MediaConvert begins processing the job\.  |  Media information, such as frame height and width, framerate, and codec\.  MediaConvert includes information for all inputs in a single event\.  | 