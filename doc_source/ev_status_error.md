# Events with ERROR status<a name="ev_status_error"></a>

MediaConvert sends the event for `ERROR` when at least one output has an error\. It contains the error code or codes, messages, and warnings or other ephemeral job information about the job's error status\. For more information about error codes, see [Error codes](mediaconvert_error_codes.md)\.

The following JSON is an example event containing the `ERROR` status for a job\.

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
        "status": "ERROR",
        "errorCode": 1040,
        "errorMessage": "Example error message",
        "userMetadata": {}
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `ERROR`\.

```
{
    "source": ["aws.mediaconvert"],
    "detail-type": ["MediaConvert Job State Change"],
    "detail": {
        "status": ["ERROR"]
    }
}
```