# CloudWatch Metrics<a name="MediaConvert-metrics"></a>

AWS Elemental MediaConvert sends the following metrics to CloudWatch every time the status of a job changes\.


| Metric | Description | 
| --- | --- | 
|  `HDOutputSeconds`  |  The number of billable seconds of HD output for a queue\. Valid Dimensions: Queue  Unit: Seconds  | 
|  `SDOutputSeconds`  |  The number of billable seconds of SD output for a queue\. Valid Dimensions: Queue Unit: Seconds  | 
|  `UHDOutputSeconds`  |  The number of billable seconds of UHD output for a queue\. Valid Dimensions: Queue Unit: Seconds   | 
|  `AudioOutputSeconds`  |  The number of billable seconds of audio output for a queue\. Valid Dimensions: Queue Unit: Seconds   | 
|  `JobsCompletedCount`  |  The number of jobs completed in this queue\. Valid Dimensions: Queue Unit: Count   | 
|  `JobsErroredCount`  |  The number of jobs that failed because of invalid inputs, such as a request to transcode a file that is not in the specified input bucket\. Valid Dimensions: Queue Unit: Count   | 
|  `StandbyTime`  |  The number of seconds before AWS Elemental MediaConvert starts transcoding a job\. Valid Dimensions: Queue Unit: Seconds   | 
|  `TranscodingTime`  |  The number of seconds for AWS Elemental MediaConvert to complete transcoding\.  Valid Dimensions: Queue  Unit: Seconds   | 
|  `Errors`  |  The number of errors caused by invalid operation parameters, such as a request for a job status that does not include the job ID\. Valid Dimensions: Operation  Unit: Count   | 

## Dimensions for AWS Elemental MediaConvert Metrics<a name="mediaconvert-metricdimensions"></a>

AWS Elemental MediaConvert metrics use the `MediaConvert` namespace and provide metrics for the following dimensions\.


| Dimension | Description | 
| --- | --- | 
|  `Queue`  |   CloudWatch shows information for the specified queue\.  | 
| Job | CloudWatch shows information only for a single job\. | 
| Operation | CloudWatch shows information only for a single operation parameter, such as a job ID\. | 