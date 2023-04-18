# Events with COMPLETE status<a name="ev_status_complete"></a>

MediaConvert sends the event for `COMPLETE` when all outputs are written to Amazon S3 without errors\. It contains both warnings and output information for the completed job\. For more information about output file names and paths, see [Output file names and paths](output-file-names-and-paths.md)\.

The following JSON is an example event containing the `COMPLETE` status for a job\.

```
{
    "version": "0",
    "id": "1234abcd-12ab-34cd-56ef-1234567890ab",
    "detail-type": "MediaConvert Job State Change",
    "source": "aws.mediaconvert",
    "account": "111122223333",
    "time": "2022-12-19T19:07:12Z",
    "region": "us-west-2",
    "resources": [
        "arn:aws:mediaconvert:us-west-2::jobs/1671476818694-phptj0"
    ],
    "detail": {
        "timestamp": 1671476832124,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1671476818694-phptj0",
        "status": "COMPLETE",
        "userMetadata": {},
        "warnings": [
            {
                "code": 000000,
                "count": 1
            }
        ],
        "outputGroupDetails": [
            {
                "outputDetails": [
                    {
                        "outputFilePaths": [
                            "s3://DOC-EXAMPLE-BUCKET/file/file.mp4"
                        ],
                        "durationInMs": 30041,
                        "videoDetails": {
                            "widthInPx": 1920,
                            "heightInPx": 1080,
                            "qvbrAvgQuality": 7.38,
                            "qvbrMinQuality": 7,
                            "qvbrMaxQuality": 8,
                            "qvbrMinQualityLocation": 2168,
                            "qvbrMaxQualityLocation": 25025
                        }
                    }
                ],
                "type": "FILE_GROUP"
            }
        ],
        "paddingInserted": 0,
        "blackVideoDetected": 10,
        "blackSegments": [
            {
                "start": 0,
                "end": 10
            }
        ]
    }
}
```

`COMPLETE` events contain additional information about your job and outputs\. The following table lists and describes the different properties available in job event message details\.


**COMPLETE event message details**  

| Property | Data type | Details | 
| --- | --- | --- | 
|  `paddingInserted`  |  integer  | The total duration of blank frames MediaConvert inserted across all outputs in your job, in milliseconds\. Video padding inserts blank frames to help keep audio and video durations aligned\. Large `paddingInserted` values show that more blank frames were inserted\. These values also show to what extend your input audio tracks start late, or end early, or both\. | 
|  `qvbrAvgQuality`  |  float  |  The average video quality of your Quality\-Defined Variable Bitrate \(QVBR\) output\. Included for QVBR outputs only\.  | 
|  `qvbrMinQuality`  |  float  |  The minimum video quality detected in your QVBR output\.  Included for QVBR outputs only\.  | 
|  `qvbrMaxQuality`  |  float  |  The maximum video quality detected in your QVBR output\. Included for QVBR outputs only\.  | 
|  `qvbrMinQualityLocation`  |  integer  |  The location in your output where `qvbrMinQuality` was detected, in milliseconds\. You can use `qvbrMinQualityLocation` while reviewing your output video quality and bandwidth usage\. Included for QVBR outputs only\.  | 
|  `qvbrMaxQualityLocation`  |  integer  |  The location in your output where `qvbrMaxQuality` was detected, in milliseconds\. You can use `qvbrMaxQualityLocation` while reviewing your output video quality and bandwidth usage\. Included for QVBR outputs only\.  | 
|  `warnings`  code  count  |  array integer integer  |  Any warning codes seen in the job and the number of times they occurred\. For more information, see [Warning codes](warning_codes.md)\.  | 
|  `blackVideoDetected`  |  integer  |  The total duration of black video frames in your outputs that are also present in your inputs, in milliseconds\. Note that `blackVideoDetected` does not include any black frames inserted by MediaConvert\.  | 
|  `blackVideoSegments`  `start`  `end`  |  array integer integer  |  The location or locations in your output where black video frames were detected\. Each segment of black video in your output is shown with its own start and end\. Note that `blackVideoSegments` does not include any black frames inserted by MediaConvert\.  | 
|  `averageBitrate`  |  integer  |  The average bitrate of your video output, calculated by dividing the duration by the total bits\.  | 

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `COMPLETE`\.

```
{
  "source": ["aws.mediaconvert"],
  "detail-type": ["MediaConvert Job State Change"],
  "detail": {
    "status": ["COMPLETE"]
  }
}
```