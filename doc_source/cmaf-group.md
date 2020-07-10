# CMAF group<a name="cmaf-group"></a>

The following example shows a CloudWatch Events `JobResult` notification, with output file path information, for a CMAF group\.

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
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        },
                        {
                            "durationInMs": 180053
                        },
                        {
                            "durationInMs": 180041,
                            "videoDetails": {
                                "widthInPx": 1280,
                                "heightInPx": 534
                            }
                        }
                    ],
                    "type": "CMAF_GROUP",
                    "playlistFilePaths": [
                        "s3://bucket/cmaf/1.mpd",
                        "s3://bucket/cmaf/1.m3u8"
                    ]
                }
            ],
            "timestamp": 1536964429367,
            "jobId": "1536964369162-gl6ur1",
            "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
            "userMetadata": {},
            "accountId": "111122223333"
        },
        "detail-type": "MediaConvert Job State Change",
        "source": "aws.mediaconvert",
        "version": "0",
        "time": "2018-09-14T22:33:49Z",
        "id": "9eb9aaae-797c-6d93-4258-3dfa6f845d64",
        "resources": [
            "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536964369162-gl6ur1"
        ]
    }
```