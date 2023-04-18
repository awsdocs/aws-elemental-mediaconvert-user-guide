# File group with a frame capture output<a name="file-group-with-frame-capture-output"></a>

This guide provides an Amazon EventBridge example event for a job with a `COMPLETE` status\. It also shows output file path information for a file group with a frame capture output\. 

A *frame capture output* is an output that you set up to create still images of video\. You set it up similar to a regular **File group** output group\. However, you remove the audio component, choose **No container** for the container, and then choose **Frame capture to JPEG** for the video codec\.

**Note**  
You can create frame capture outputs only in jobs that also have a regular audio and video output\. MediaConvert doesn't support jobs that consist only of a frame capture output\.

When you create a frame capture output, the `COMPLETE` status includes the `outputFilePaths` property\. This tells you the file name and path of the final captured image\. 

**Tip**  
Because the service includes automatic numbering in the frame capture file names, you can infer all the image names from the final one\. For example, if your `outputFilePaths` value is `s3://DOC-EXAMPLE-BUCKET/frameoutput/file.0000036.jpg`, you can infer that there are 35 other images in the same location, named `file.0000001`, `file.0000002`, and so on\.

The following is an EventBridge sample event for a job with a `COMPLETE` status\. It includes output file path information for a file group with a frame capture output\. 

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
                            "s3://DOC-EXAMPLE-BUCKET/frameoutput/file.0000036.jpg"
                        ],
                        "durationInMs": 185000,
                        "videoDetails": {
                            "widthInPx": 1280,
                            "heightInPx": 720
                        }
                    }
                ],
                "type": "FILE_GROUP"
            },
            {
                "outputDetails": [
                    {
                        "outputFilePaths": [
                            "s3://DOC-EXAMPLE-BUCKET/file/file.mp4"
                        ],
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