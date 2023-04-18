# Events with CANCELED status<a name="ev_status_canceled"></a>

MediaConvert sends the event for `CANCELED` when the job is canceled\. It contains basic job details including `timestamp`, `accountID`, `queue`, `jobId`, and `userMetadata`\.

The following JSON is an example event containing the `CANCELED` status for a job\.

```
{
    "version": "0",
    "id": "1234abcd-12ab-34cd-56ef-1234567890ab",
    "detail-type": "MediaConvert Job State Change",
    "source": "aws.mediaconvert",
    "account": "111122223333",
    "time": "2018-01-07T23:35:20Z",
    "region": "us-west-2",
    "resources": ["arn:aws:mediaconvert:us-west-2:111122223333:jobs/1515368087458-qnoxtd"],
    "detail": {
        "timestamp": 1515368120764,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1515368087458-qnoxtd",
        "status": "CANCELED",
        "userMetadata": {}
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `CANCELED`\.

```
{
    "source": ["aws.mediaconvert"],
    "detail-type": ["MediaConvert Job State Change"],
    "detail": {
        "status": ["CANCELED"]
    }
}
```