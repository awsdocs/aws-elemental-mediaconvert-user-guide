# File group<a name="file-group"></a>

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
                                "s3://bucket/frameoutput/file.0000036.jpg"
                            ],
                            "durationInMs": 185000,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        }
                    ],
                    "type": "FILE_GROUP"
                },
                {
                    "outputDetails": [
                        {
                            "outputFilePaths": [
                                "s3://bucket/file/file.mp4"
                            ],
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        }
                    ],
                    "type": "FILE_GROUP"
                }
            ],
            "timestamp": 1536962166536,
            "jobId": "1536962115049-g58xc4",
            "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
            "userMetadata": {},
            "accountId": "111122223333"
        },
        "detail-type": "MediaConvert Job State Change",
        "source": "aws.mediaconvert",
        "version": "0",
        "time": "2018-09-14T21:56:06Z",
        "id": "cd06e4d1-f663-9b04-48d6-ec2a97cbe54a",
        "resources": [
            "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536962115049-g58xc4"
        ]
    }
```