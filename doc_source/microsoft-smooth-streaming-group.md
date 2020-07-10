# Microsoft Smooth Streaming group<a name="microsoft-smooth-streaming-group"></a>

```
{
        "account": "111122223333",
        "region": "us-west-2",
        "detail": {
            "status": "COMPLETE",
            "outputGroupDetails": [
                {
                    "outputDetails": [
                        {
                            "outputFilePaths": [
                                "s3://bucket/smooth/1_va.ismv"
                            ],
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        },
                        {
                            "outputFilePaths": [
                                "s3://bucket/smooth/2_va.ismv"
                            ],
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        }
                    ],
                    "type": "MS_SMOOTH_GROUP",
                    "playlistFilePaths": [
                        "s3://bucket/smooth/1.ism"
                    ]
                }
            ],
            "timestamp": 1536964409174,
            "jobId": "1536964355034-rqbv0o",
            "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
            "userMetadata": {},
            "accountId": "111122223333"
        },
        "detail-type": "MediaConvert Job State Change",
        "source": "aws.mediaconvert",
        "version": "0",
        "time": "2018-09-14T22:33:29Z",
        "id": "7569da66-f500-1af4-082b-da6c756e6813",
        "resources": [
            "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536964355034-rqbv0o"
        ]
    }
```