# DASH ISO group<a name="dash-iso-group"></a>

The following example shows a CloudWatch Events `JobResult` notification, with output file path information, for a DASH ISO group\.

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
                        }
                    ],
                    "type": "DASH_ISO_GROUP",
                    "playlistFilePaths": [
                        "s3://bucket/dash/1.mpd"
                    ]
                }
            ],
            "timestamp": 1536964380391,
            "jobId": "1536964333549-opn151",
            "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
            "userMetadata": {},
            "accountId": "111122223333"
        },
        "detail-type": "MediaConvert Job State Change",
        "source": "aws.mediaconvert",
        "version": "0",
        "time": "2018-09-14T22:33:00Z",
        "id": "020901de-2b47-9e52-a2a7-b843b053bcba",
        "resources": [
            "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1536964333549-opn151"
        ]
    }
```