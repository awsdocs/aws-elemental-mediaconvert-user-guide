# Events with INPUT\_INFORMATION status<a name="ev_status_input_information"></a>

MediaConvert sends the event for `INPUT_INFORMATION` after a job begins processing and after MediaConvert reads information about your input\. The event primarily contains media information about your input, such as frame height and width, frame rate, and codec\.

 MediaConvert includes information about all of your inputs in a single event\.

The following JSON is an example event containing the `INPUT_INFORMATION` status for a job with a single input\.

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
        "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1671476818694-phptj0"
    ],
    "detail": {
        "timestamp": 1671476832075,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1671476818694-phptj0",
        "status": "INPUT_INFORMATION",
        "userMetadata": {},
        "inputDetails": [
            {
                "id": 1,
                "uri": "s3://DOC-EXAMPLE-BUCKET/file/file.mp4",
                "audio": [
                    {
                        "channels": 2,
                        "codec": "AAC",
                        "language": "UND",
                        "sampleRate": 44100,
                        "streamId": 2
                    }
                ],
                "video": [
                    {
                        "bitDepth": 8,
                        "codec": "H_264",
                        "colorFormat": "YUV_420",
                        "fourCC": "avc1",
                        "frameRate": 24,
                        "height": 1080,
                        "interlaceMode": "PROGRESSIVE",
                        "sar": "1:1",
                        "standard": "UNSPECIFIED",
                        "streamId": 1,
                        "width": 1920
                    }
                ]
            }
        ]
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `INPUT_INFORMATION`\.

```
{
  "source": ["aws.mediaconvert"],
  "detail-type": ["MediaConvert Job State Change"],
  "detail": {
    "status": ["INPUT_INFORMATION"]
  }
}
```