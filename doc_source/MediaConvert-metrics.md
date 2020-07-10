# Using CloudWatch metrics to view metrics for AWS Elemental MediaConvert resources<a name="MediaConvert-metrics"></a>

AWS Elemental MediaConvert sends the following metrics to CloudWatch every time the status of a job changes\.


| Metric | Description | 
| --- | --- | 
|  `AudioOutputDuration`  |  The number of seconds of audio\-only output for a queue\. Valid dimensions: Queue Unit: Seconds   | 
|  `SDOutputDuration`  |  The number of seconds of standard definition \(SD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\. Valid dimensions: Queue Unit: Seconds  | 
|  `HDOutputDuration`  |  The number of seconds of high\-definition \(HD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\. Valid dimensions: Queue Unit: Seconds  | 
|  `UHDOutputDuration`  |  The number of seconds of ultra\-high\-definition \(UHD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\. Valid dimensions: Queue Unit: Seconds   | 
|  `8KOutputDuration`  |  The number of seconds of 8K output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\. Valid dimensions: Queue Unit: Seconds   | 
|  `JobsCompletedCount`  |  The number of jobs completed in this queue\. Valid dimensions: Queue Unit: Count   | 
|  `JobsErroredCount`  |  The number of jobs that failed because of invalid inputs, such as a request to transcode a file that is not in the specified input bucket\. Valid dimensions: Queue Unit: Count   | 
|  `StandbyTime`  |  The number of seconds before AWS Elemental MediaConvert starts transcoding a job\. Valid dimensions: Queue Unit: Seconds   | 
|  `TranscodingTime`  |  The number of seconds for AWS Elemental MediaConvert to complete transcoding\.  Valid dimensions: Queue  Unit: Seconds   | 

## Dimensions for AWS Elemental MediaConvert metrics<a name="mediaconvert-metricdimensions"></a>

AWS Elemental MediaConvert metrics use the `MediaConvert` namespace and provides metrics for the following dimensions\.


| Dimension | Description | 
| --- | --- | 
|  `Queue`  |   CloudWatch shows information for the specified queue\.  | 
|  `Job`  |  CloudWatch shows information only for a single job\.  | 
|  `Operation`  |  CloudWatch shows information only for a single operation parameter, such as a job ID\.  | 