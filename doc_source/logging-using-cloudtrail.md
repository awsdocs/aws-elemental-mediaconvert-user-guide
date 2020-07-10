# Logging MediaConvert API calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

MediaConvert is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in MediaConvert\. CloudTrail captures all API calls for MediaConvert as events, including calls from the MediaConvert console and from code calls to the MediaConvert APIs\. If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, including events for MediaConvert\. If you don't configure a trail, you can still view the most recent events in the CloudTrail console in **Event history**\. Using the information collected by CloudTrail, you can determine the request that was made to MediaConvert, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, see the [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## MediaConvert information in CloudTrail<a name="service-name-info-in-cloudtrail"></a>

CloudTrail is enabled on your AWS account when you create the account\. When activity occurs in MediaConvert, that activity is recorded in a CloudTrail event along with other AWS service events in **Event history**\. You can view, search, and download recent events in your AWS account\. For more information, see [Viewing events with CloudTrail event history](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)\. 

For an ongoing record of events in your AWS account, including events for MediaConvert, create a trail\. A trail enables CloudTrail to deliver log files to an Amazon S3 bucket\. By default, when you create a trail in the console, the trail applies to all regions\. The trail logs events from all regions in the AWS partition and delivers the log files to the Amazon S3 bucket that you specify\. Additionally, you can configure other AWS services to further analyze and act upon the event data collected in CloudTrail logs\. For more information, see: 
+ [Overview for creating a trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-and-update-a-trail.html)
+ [CloudTrail supported services and integrations](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html#cloudtrail-aws-service-specific-topics-integrations)
+ [Configuring Amazon SNS notifications for CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)
+ [Receiving CloudTrail log files from multiple regions](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html) and [Receiving CloudTrail log files from multiple accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)

All MediaConvert actions are logged by CloudTrail and are documented in the [AWS Elemental MediaConvert API reference](https://docs.aws.amazon.com/mediaconvert/latest/apireference/)\. For example, calls to the `DeleteQueue`, `CreateQueue`, and `TagResource` operations generate entries in the CloudTrail log files\. 

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 
+ Whether the request was made with root or IAM user credentials\.
+ Whether the request was made with temporary security credentials for a role or federated user\.
+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity element](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

## Understanding MediaConvert log file entries<a name="understanding-service-name-entries"></a>

A trail is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files are not an ordered stack trace of the public API calls, so they do not appear in any specific order\. 

The following examples show CloudTrail log entries that demonstrate the `DeleteQueue`, `CreateQueue`, and `TagResource` actions\.

**Example log entry: DeleteQueue**

```
      {
    "eventVersion": "1.05",
    "userIdentity": {
        "type": "IAMUser",
        "principalId": "AIDACKCEVSQ6C2EXAMPLE",
        "arn": "arn:aws:iam::111122223333:user/testuser",
        "accountId": "111122223333",
        "accessKeyId": "AIDACKCEVSQ6C2EXAMPLE",
        "userName": "testuser",
        "sessionContext": {
            "attributes": {
                "mfaAuthenticated": "false",
                "creationDate": "2018-07-10T14:01:57Z"
            }
        },
        "invokedBy": "signin.amazonaws.com"
    },
    "eventTime": "2018-07-10T15:36:29Z",
    "eventSource": "mediaconvert.amazonaws.com",
    "eventName": "DeleteQueue",
    "awsRegion": "eu-west-1",
    "sourceIPAddress": "203.0.113.0.186",
    "userAgent": "signin.amazonaws.com",
    "requestParameters": {
        "name": "8"
    },
    "responseElements": null,
    "requestID": "03691738-8457-11e8-a138-2b67258eef82",
    "eventID": "e7d85e26-6c96-4242-80f8-6c8074c26253",
    "readOnly": false,
    "eventType": "AwsApiCall",
    "recipientAccountId": "111122223333"
}
```

**Example log entry: CreateQueue**

```
      {
    "eventVersion": "1.05",
    "userIdentity": {
        "type": "IAMUser",
        "principalId": "AIDACKCEVSQ6C2EXAMPLE",
        "arn": "arn:aws:iam::111122223333:user/jeremyj",
        "accountId": "111122223333",
        "accessKeyId": "AIDACKCEVSQ6C2EXAMPLE",
        "userName": "testUser",
        "sessionContext": {
            "attributes": {
                "mfaAuthenticated": "false",
                "creationDate": "2018-07-10T14:01:57Z"
            }
        },
        "invokedBy": "signin.amazonaws.com"
    },
    "eventTime": "2018-07-10T16:49:13Z",
    "eventSource": "mediaconvert.amazonaws.com",
    "eventName": "CreateQueue",
    "awsRegion": "eu-west-1",
    "sourceIPAddress": "54.240.197.6",
    "userAgent": "signin.amazonaws.com",
    "requestParameters": {
        "name": "TestTag2",
        "description": "",
        "tags": {}
    },
    "responseElements": {
        "queue": {
            "arn": "arn:aws:mediaconvert:eu-west-1:111122223333:queues/TestTag2",
            "createdAt": 1531241353,
            "lastUpdated": 1531241353,
            "type": "CUSTOM",
            "status": "ACTIVE",
            "description": "",
            "name": "TestTag2",
            "submittedJobsCount": 0,
            "progressingJobsCount": 0
        }
    },
    "requestID": "2ccb3914-8461-11e8-bcb3-8578a1397527",
    "eventID": "a0ff791e-e676-4070-a296-67ecdaa662b1",
    "readOnly": false,
    "eventType": "AwsApiCall",
    "recipientAccountId": "111122223333"
}
```

**Example log entry: TagResource**

```
      {
    "eventVersion": "1.05",
    "userIdentity": {
        "type": "IAMUser",
        "principalId": "AIDACKCEVSQ6C2EXAMPLE",
        "arn": "arn:aws:iam::111122223333:user/testuser",
        "accountId": "111122223333",
        "accessKeyId": "AIDACKCEVSQ6C2EXAMPLE",
        "userName": "testuser"
    },
    "eventTime": "2018-07-10T18:44:27Z",
    "eventSource": "mediaconvert.amazonaws.com",
    "eventName": "TagResource",
    "awsRegion": "eu-west-1",
    "sourceIPAddress": "203.0.113.0.186",
    "userAgent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36",
    "requestParameters": {
        "arn": "arn:aws:mediaconvert:eu-west-1:111122223333:queues/1",
        "Tags": {
            "CostCenter": "BU-Test"
        }
    },
    "responseElements": null,
    "requestID": "462fd283-8471-11e8-b353-03144533ee8a",
    "eventID": "3364cb1b-79c8-4081-9aa0-1b0677349d5e",
    "readOnly": false,
    "eventType": "AwsApiCall",
    "recipientAccountId": "111122223333"
}
}
```