# Apple HLS group<a name="apple-hls-group"></a>

The following example shows a CloudWatch Events `JobResult` notification, with output file path information, for an Apple HLS group\.

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
                                "s3://bucket/hls/mainv2.m3u8"
                            ],
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 480,
                                "heightInPx": 270
                            }
                        },
                        {
                            "durationInMs": 180053
                        },
                        {
                            "outputFilePaths": [
                                "s3://bucket/hls/mainv1.m3u8"
                            ],
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        }
                    ],
                    "type": "HLS_GROUP",
                    "playlistFilePaths": [
                        "s3://bucket/hls/main.m3u8"
                    ]
                }
            ],
            "timestamp": 1536962071281,
            "jobId": "1536961999428-kxngbl",
            "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
            "userMetadata": {},
            "accountId": "111122223333"
        },
        "detail-type": "MediaConvert Job State Change",
        "source": "aws.mediaconvert",
        "version": "0",
        "time": "2018-09-14T21:54:31Z",
        "id": "63ea01c2-3e65-8996-9588-a9d18a3d63fe",
        "resources": [
            "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536961999428-kxngbl"
        ]
    }
```