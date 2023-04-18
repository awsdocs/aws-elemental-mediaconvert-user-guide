# Events with NEW\_WARNING status<a name="ev_status_new_warning"></a>

MediaConvert sends an event for `NEW_WARNING` when a warning condition arises\. A warning condition doesn't stop the job from running\. It contains the submission queue ARN, the job ID, and a warning message\. Warning messages inform you about conditions that don't stop the job but may indicate that the job is not progressing as you planned\.

For example, a job that you set up to hop queues reaches the wait time that you specified, but can't hop\.

`NEW_WARNING` only contains the most recent warning message\. It doesn't report previous warnings, even if those warning conditions are still in effect\.

The following JSON is an example event containing the `NEW_WARNING` status for a job\.

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
        "status": "NEW_WARNING",
        "warningCode": "000000",
        "warningMessage": "Example warning message",
        "userMetadata": {}
    }
}
```

You can use the following sample JSON to create an EventBridge event pattern for jobs with a status of `NEW_WARNING`\.

```
{
  "source": ["aws.mediaconvert"],
  "detail-type": ["MediaConvert Job State Change"],
  "detail": {
    "status": ["NEW_WARNING"]
  }
}
```