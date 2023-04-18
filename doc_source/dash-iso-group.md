# DASH ISO group<a name="dash-iso-group"></a>

The following is an Amazon EventBridge sample event for a job with a `COMPLETE` status\. It includes output file path information for a DASH ISO group\.

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
                        "durationInMs": 180041,
                        "blackVideoDurationInMs": 0,
                        "videoDetails": {
                            "widthInPx": 1280,
                            "heightInPx": 720,
                            "averageQVBRScore": 7.38,
                            "minimumQVBRScore": 7,
                            "maximumQVBRScore": 8,
                            "minimumQVBRScoreLocationInMs": 2168,
                            "maximumQVBRScoreLocationInMs": 25025
                        }
                    }
                ],
                "type": "DASH_ISO_GROUP",
                "playlistFilePaths": [
                    "s3://DOC-EXAMPLE-BUCKET/dash/1.mpd"
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