# Events with PROGRESSING status<a name="ev_status_progressing"></a>

MediaConvert sends the event for `PROGRESSING` when a job moves from the `SUBMITTED` state to the `PROGRESSING` state\.

**Note**  
After a job has been in the `PROGRESSING` status for 48 hours, the service puts it into an `ERROR` state and stops working on it\. You are not billed for jobs that end in an `ERROR` state\.

The following JSON is an example event containing the `PROGRESSING` status for a job\.

```
{
    "version": "0",
    "id": "1234abcd-12ab-34cd-56ef-1234567890ab",
    "detail-type": "MediaConvert Job State Change",
    "source": "aws.mediaconvert",
    "account": "111122223333",
    "time": "2022-12-19T19:20:21Z",
    "region": "us-west-2",
    "resources": [
        "arn:aws:mediaconvert:us-west-2:111122223333:jobs/1671477617078-2886ye"
    ],
    "detail": {
        "timestamp": 1671477621654,
        "accountId": "111122223333",
        "queue": "arn:aws:mediaconvert:us-west-2:111122223333:queues/Default",
        "jobId": "1671477617078-2886ye",
        "status": "PROGRESSING",
        "userMetadata": {}
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `PROGRESSING`\.

```
{
    "source": ["aws.mediaconvert"],
    "detail-type": ["MediaConvert Job State Change"],
    "detail": {
        "status": ["PROGRESSING"]
    }
}
```