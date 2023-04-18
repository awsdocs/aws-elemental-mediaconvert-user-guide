# List of MediaConvert CloudWatch metrics<a name="metrics"></a>

AWS Elemental MediaConvert sends the following metrics to CloudWatch at the end of every job\.


| Metric name | Unit | Description | 
| --- | --- | --- | 
|  `Errors`  | Count | Tracks errors encountered when making a particular API call\.Operations include: `CreateJob`, `GetJob`, `ListJobs`, `ListPresets`, `ListQueues`, `ListTagsForResource`, and `Subscribe` | 
|  `AudioOutputDuration`  | Milliseconds |  The number of milliseconds of audio\-only output for a queue\.  | 
|  `SDOutputDuration`  | Milliseconds |  The number of milliseconds of standard definition \(SD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\.  | 
|  `HDOutputDuration`  | Milliseconds |  The number of milliseconds of high\-definition \(HD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\.  | 
|  `UHDOutputDuration`  | Milliseconds |  The number of milliseconds of ultra\-high\-definition \(UHD\) output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\.  | 
|  `8KOutputDuration`  | Milliseconds |  The number of milliseconds of 8K output for a queue\. For the definition of each video resolution category, see the [AWS Elemental MediaConvert pricing page](https://aws.amazon.com/mediaconvert/pricing)\.  | 
|  `JobsCompletedCount`  | Count |  The number of jobs completed in a queue\.  | 
|  `JobsCanceled`  | Count |  The number of jobs canceled in a queue\.  | 
|  `JobsErroredCount`  | Count |  The number of jobs that failed because of invalid inputs, such as a request to transcode a file that is not in the specified input bucket\.  | 
|  `StandbyTime`  | Milliseconds |  The amount of time before MediaConvert starts transcoding a job, in milliseconds\.  | 
|  `TranscodingTime`  | Milliseconds |  The number of milliseconds for MediaConvert to complete transcoding\.  | 
|  `BlackVideoDetected`  | Milliseconds |  The total duration of black video frames in your output that are also present in your input in milliseconds\. Note that `BlackVideoDetected` does not include any black frames inserted by MediaConvert\.  | 
|  `BlackVideoDetectedRatio`  | Ratio |  The ratio of black video frames to the total duration of your output\. Higher ratios show outputs with more black frames\.  | 
|  `LongestBlackSegmentDetected`  | Milliseconds |  The location in your output with the longest continuous segment of black video frames, in milliseconds\.  | 
|  `VideoPaddingInserted`  | Milliseconds |  The total duration of blank frames MediaConvert inserted across all outputs in your job, in milliseconds\. Video padding inserts blank frames to help keep audio and video durations aligned\. Large `VideoPaddingInserted` values show that more blank frames were inserted\. They also show to what extent your input audio tracks either start late, end early, or both\.  | 
|  `VideoPaddingInsertedRatio`  | Ratio |  The ratio of blank frames MediaConvert inserted to the overall duration of your output\. Higher ratios may signal audio video sync issues in your input\.  | 
|  `AvgBitrateTop`  | Bits per second |  The average bitrate of the highest bitrate output in the output group\.  | 
|  `AvgBitrateBottom`  | Bits per second |  The average bitrate of the lowest bitrate output in the output group\.  | 
|  `QVBRAvgQualityHighBitrate`  | Score |  The average QVBR quality score of the highest bitrate output in the output group\.  | 
|  `QVBRAvgQualityLowBitrate`  | Score |  The average QVBR quality score of the lowest bitrate output in the output group\.  | 
|  `QVBRMinQualityHighBitrate`  | Score |  The minimum QVBR quality score of the highest bitrate output in the output group\.  | 
|  `QVBRMinQualityLowBitrate`  | Score |  The minimum QVBR quality score of the lowest bitrate output in the output group\.  | 