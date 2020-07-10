# File group with a frame capture output<a name="file-group-with-frame-capture-output"></a>

A *frame capture output* is an output that you set up to create \.jpeg still images of each I\-frame in your video\. You set it up like a regular **File group** output group, except that you remove the audio component, choose **No container** for the container, and then choose **Frame capture to JPEG** for the video codec\.

**Note**  
You can create frame capture outputs only in jobs that also have a regular audio and video output\. MediaConvert doesn't support jobs that consist only of a frame capture output\.

When you create a frame capture output, the `JobResult` includes the `outputFilePaths` property, which tells you the file name and path of the final captured image\. 

**Tip**  
Because the service includes automatic numbering in the frame capture file names, you can infer all the image names from the final one\. For example, if your `outputFilePaths` value is `s3://bucket/frameoutput/file.0000036.jpg`, you can infer that there are 35 other images in the same location, named `file.0000001`, `file.0000002`, and so on\.

The following example shows a CloudWatch Events `JobResult` notification, with output file path information, for a file group with a frame capture output\. 

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