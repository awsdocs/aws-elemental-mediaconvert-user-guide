# Events with STATUS\_UPDATE status<a name="ev_status_status_update"></a>

MediaConvert sends the event for `STATUS_UPDATE` approximately one minute after it begins processing a job\. By default, updates are sent approximately every minute after that, until the service finishes transcoding or encounters an error\.

You can optionally specify a different update frequency in your job, with the **Status update interval** setting\. For more frequent updates, you can choose 10, 12, 15, 20, or 30 seconds\. For fewer updates, you can choose anywhere from 2 to 10 minutes, in increments of one minute\. For more information, see [Adjust the status update interval](adjusting-the-status-update-interval.md)\.

A `STATUS_UPDATE` event contains information about your job's current phase\. When available, it contains job and phase percent completion\.

Job phases are as follows:
+ During `PROBING`, the service reads information about the input while it prepares to transcode\. 
+ During `TRANSCODING`, the service demuxes, decodes, encodes, and remuxes your content\. In some jobs, the service begins uploading outputs to your output Amazon S3 bucket during this phase, as well\. The phase ends when all transcoding is complete\.
+ During `UPLOADING`, the service uploads the remaining transcoded outputs to your Amazon S3 bucket\.

The following JSON is an example event containing the `STATUS_UPDATE` status for a job\.

```
{
    "version": "0",
    "id": "1234abcd-12ab-34cd-56ef-1234567890ab",
    "detail-type": "MediaConvert Job State Change",
    "source": "aws.mediaconvert",
    "account": "111122223333",
    "time": "2022-12-19T19:21:21Z",
    "region": "us-west-2",
    "resources": [
        "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1671477617078-2886ye"
    ],
    "detail": {
        "timestamp": 1671477681737,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1671477617078-2886ye",
        "status": "STATUS_UPDATE",
        "userMetadata": {},
        "framesDecoded": 353,
        "jobProgress": {
            "phaseProgress": {
                "PROBING": {
                    "status": "COMPLETE",
                    "percentComplete": 100
                },
                "TRANSCODING": {
                    "status": "PROGRESSING",
                    "percentComplete": 2
                },
                "UPLOADING": {
                    "status": "PENDING",
                    "percentComplete": 0
                }
            },
        "jobPercentComplete": 7,
        "currentPhase": "TRANSCODING",
        "retryCount": 0
        }
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `STATUS_UPDATE`\.

```
{
    "source": ["aws.mediaconvert"],
    "detail-type": ["MediaConvert Job State Change"],
    "detail": {
        "status": ["STATUS_UPDATE"]
    }
}
```