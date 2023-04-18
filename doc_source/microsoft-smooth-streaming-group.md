# Microsoft Smooth Streaming group<a name="microsoft-smooth-streaming-group"></a>

The following is an EventBridge sample event for a job with a `COMPLETE` status\. It includes output file path information for a Microsoft Smooth Streaming group\.

```
{
    "detail": {
        "status": "COMPLETE",
        "paddingInserted": 0,
        "blackVideoDetected": 10,
        "blackSegments": [
            {
                "start": 0,
                "end": 10
            }
        ],
        "outputGroupDetails": [
            {
                "outputDetails": [
                    {
                        "outputFilePaths": [
                            "s3://DOC-EXAMPLE-BUCKET/smooth/1_va.ismv"
                        ],
                        "durationInMs": 180041,
                        "blackVideoDurationInMs": 0,
                        "videoDetails": {
                            "widthInPx": 1280,
                            "heightInPx": 534,
                            "averageQVBRScore": 7.38,
                            "minimumQVBRScore": 7,
                            "maximumQVBRScore": 8,
                            "minimumQVBRScoreLocationInMs": 2168,
                            "maximumQVBRScoreLocationInMs": 25025
                        }
                    }
                ],
                "type": "MS_SMOOTH_GROUP",
                "playlistFilePaths": [
                    "s3://DOC-EXAMPLE-BUCKET/smooth/1.ism"
                ]
            }
        ],
        "timestamp": 1536964380391,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1536964333549-opn151",
        "userMetadata": {},
        "warnings": [
            {
                "code": 000000,
                "count": 1
            }
        ]
    },
    "version": "0",
    "id": "1234abcd-12ab-34cd-56ef-1234567890ab",
    "detail-type": "MediaConvert Job State Change",
    "source": "aws.mediaconvert",
    "account": "111122223333",
    "time": "2018-09-14T21:54:31Z",
    "region": "us-west-2",
    "resources": [
        "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536961999428-kxngbl"
    ]
}
```

**Note**  
Quality\-Defined Variable Bitrate \(QVBR\) statistics are only available when your video output uses QVBR rate control\.