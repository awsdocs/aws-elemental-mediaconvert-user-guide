# File group<a name="file-group"></a>

The following is an Amazon EventBridge sample event for a job with a `COMPLETE` status\. The example includes output file path information for a file group\.

```
{
    "detail": {
        "status": "COMPLETE",
        "paddingInserted": 0,
        "blackVideoDetected": 10,
        "blackSegments": [
            "start": 0,
            "end": 10
        ],
        "outputGroupDetails": [
            {
                "outputDetails": [
                    {
                        "outputFilePaths": [
                            "s3://DOC-EXAMPLE-BUCKET/file/file.mp4"
                        ],
                        "durationInMs": 180041,
                        "videoDetails": {
                            "averageBitrate": 200000,
                            "widthInPx": 1280,
                            "heightInPx": 720,
                            "qvbrAvgQuality": 7.38,
                            "qvbrMinQuality": 7,
                            "qvbrMaxQuality": 8,
                            "qvbrMinQualityLocation": 2168,
                            "qvbrMaxQualityLocation": 25025
                        },
                    }
                ],
                "type": "FILE_GROUP"
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
        ],
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
QVBR statistics are only available when your video output uses Quality\-Defined Variable Bitrate \(QVBR\) rate control\.