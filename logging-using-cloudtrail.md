# Logging AWS Elemental MediaConvert API Calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

AWS Elemental MediaConvert is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in AWS Elemental MediaConvert\. If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, Amazon CloudWatch Logs, and Amazon CloudWatch Events\. AWS Elemental MediaConvert is also integrated with the **Event history** feature in CloudTrail\. If an API for AWS Elemental MediaConvert is supported in **Event history**, you can view the most recent seven days of events in AWS Elemental MediaConvert in the CloudTrail console in **Event history** even if you have not configured any logs in CloudTrail\. Using the information collected by CloudTrail, you can determine the request that was made to AWS Elemental MediaConvert, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, including how to configure and enable it, see the [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## AWS Elemental MediaConvert Information in CloudTrail<a name="service-name-info-in-cloudtrail"></a>

CloudTrail is enabled on your AWS account when you create the account\. When activity occurs in AWS Elemental MediaConvert, that activity is recorded in a CloudTrail event along with other AWS service events in **Event history**\. You can view, search, and download the past seven days of supported activity in your AWS account\. For more information, see [Viewing Events with CloudTrail Event History](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) and [Services Supported by CloudTrail Event History](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events-supported-services.html)\. 

All AWS Elemental MediaConvert actions are logged by CloudTrail and are documented in the AWS Elemental MediaConvert [API Reference](http://docs.aws.amazon.com/mediaconvert/latest/apireference/welcome.html)\. For example, calls to the `CreateJob`, `ListPresets` and `DeleteQueue` sections generate entries in the CloudTrail log files\. 

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 

+ Whether the request was made with root or IAM user credentials\.

+ Whether the request was made with temporary security credentials for a role or federated user\.

+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity Element](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

You can view, search, and download the most recent seven days of AWS Elemental MediaConvert activity in the CloudTrail console\. For more information, see [Viewing Events with CloudTrail Event History](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)\. You can also create a trail and store your log files in your Amazon S3 bucket for as long as you want, and define Amazon S3 lifecycle rules to archive or delete log files automatically\. By default, your log files are encrypted with Amazon S3 server\-side encryption \(SSE\)\.

To be notified of log file delivery, configure CloudTrail to publish Amazon SNS notifications when new log files are delivered\. For more information, see [Configuring Amazon SNS Notifications for CloudTrail](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)\.

You can also aggregate AWS Elemental MediaConvert log files from multiple AWS regions and multiple AWS accounts into a single Amazon S3 bucket\. 

For more information, see [Receiving CloudTrail Log Files from Multiple Regions](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html) and [Receiving CloudTrail Log Files from Multiple Accounts](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)\.

## Understanding AWS Elemental MediaConvert Log File Entries<a name="understanding-service-name-entries"></a>

A trail is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files are not an ordered stack trace of the public API calls, so they do not appear in any specific order\. 

The following example shows a CloudTrail log entry that demonstrates the CreateJob action\.

```
      {
   "eventVersion":"1.05",
   "userIdentity":{
      "type":"IAMUser",
      "principalId":"ABCDEFGHIJKL123456789",
      "arn":"arn:aws:iam::123456789000:user/testuser",
      "accountId":"123456789000",
      "accessKeyId":"ABCDE12345EFGHIJKLMN",
      "userName":"test user"
   },
   "eventTime":"2017-11-15T02:57:32Z",
   "eventSource":"mediaconvert.amazonaws.com",
   "eventName":"CreateJob",
   "awsRegion":"us-west-2",
   "sourceIPAddress":"1.2.3.4",
   "userAgent":"PostmanRuntime/6.1.6",
   "requestParameters":{
      "settings":{
         "outputGroups":[
            {
               "customName":"test",
               "name":"DASH ISO",
               "outputs":[
                  {
                     "containerSettings":{
                        "container":"MPD"
                     },
                     "videoDescription":{
                        "scalingBehavior":"DEFAULT",
                        "timecodeInsertion":"DISABLED",
                        "antiAlias":"ENABLED",
                        "sharpness":50,
                        "codecSettings":{
                           "codec":"H_264",
                           "h264Settings":{
                              "interlaceMode":"PROGRESSIVE",
                              "numberReferenceFrames":1,
                              "syntax":"DEFAULT",
                              "softness":0,
                              "gopClosedCadence":1,
                              "gopSize":90,
                              "slices":1,
                              "gopBReference":"DISABLED",
                              "slowPal":"DISABLED",
                              "spatialAdaptiveQuantization":"ENABLED",
                              "temporalAdaptiveQuantization":"ENABLED",
                              "flickerAdaptiveQuantization":"ENABLED",
                              "entropyEncoding":"CABAC",
                              "bitrate":5000000,
                              "framerateControl":"INITIALIZE_FROM_SOURCE",
                              "rateControlMode":"CBR",
                              "codecProfile":"MAIN",
                              "telecine":"NONE",
                              "minIInterval":0,
                              "adaptiveQuantization":"MEDIUM",
                              "codecLevel":"AUTO",
                              "fieldEncoding":"PAFF",
                              "sceneChangeDetect":"ENABLED",
                              "qualityTuningLevel":"SINGLE_PASS",
                              "framerateConversionAlgorithm":"DUPLICATE_DROP",
                              "unregisteredSeiTimecode":"DISABLED",
                              "gopSizeUnits":"FRAMES",
                              "parControl":"INITIALIZE_FROM_SOURCE",
                              "numberBFramesBetweenReferenceFrames":2,
                              "repeatPps":"DISABLED"
                           }
                        },
                        "afdSignaling":"NONE",
                        "dropFrameTimecode":"ENABLED",
                        "respondToAfd":"NONE",
                        "colorMetadata":"INSERT"
                     },
                     "audioDescriptions":[
                        {
                           "audioTypeControl":"FOLLOW_INPUT",
                           "codecSettings":{
                              "codec":"AAC",
                              "aacSettings":{
                                 "audioDescriptionBroadcasterMix":"NORMAL",
                                 "bitrate":96000,
                                 "rateControlMode":"CBR",
                                 "codecProfile":"LC",
                                 "codingMode":"CODING_MODE_2_0",
                                 "rawFormat":"NONE",
                                 "sampleRate":48000,
                                 "specification":"MPEG4"
                              }
                           },
                           "languageCodeControl":"FOLLOW_INPUT"
                        }
                     ],
                     "nameModifier":"aaa"
                  }
               ],
               "outputGroupSettings":{
                  "type":"DASH_ISO_GROUP_SETTINGS",
                  "dashIsoGroupSettings":{
                     "segmentLength":30,
                     "destination":"s3://testuser-testuser/clip01.mp4",
                     "encryption":"***",
                     "fragmentLength":2,
                     "segmentControl":"SINGLE_FILE",
                     "hbbtvCompliance":"NONE"
                  }
               }
            }
         ],
         "adAvailOffset":0,
         "inputs":[
            {
               "audioSelectors":{
                  "Audio Selector 1":{
                     "offset":0,
                     "defaultSelection":"DEFAULT",
                     "programSelection":1
                  }
               },
               "videoSelector":{
                  "colorSpace":"FOLLOW"
               },
               "filterEnable":"AUTO",
               "psiControl":"USE_PSI",
               "filterStrength":0,
               "deblockFilter":"DISABLED",
               "denoiseFilter":"DISABLED",
               "timecodeSource":"EMBEDDED",
               "fileInput":"s3://mediaconvert-testuser/clip01.mp4"
            }
         ]
      },
      "role":"arn:aws:iam::123456789000:role/ecsInstanceRole",
      "userMetadata":{
         "Name":"Prod"
      },
      "queue":"arn:aws:mediaconvert:us-west-2:123456789000:queues/Default"
   },
   "responseElements":{
      "job":{
         "arn":"arn:aws:mediaconvert:us-west-2:123456789000:jobs/1510714652428-jyvx95",
         "id":"1510714652428-jyvx95",
         "createdAt":1510714652436,
         "queue":"arn:aws:mediaconvert:us-west-2:123456789000:queues/Default",
         "userMetadata":{
            "Name":"Prod"
         },
         "role":"arn:aws:iam::123456789000:role/ecsInstanceRole",
         "settings":{
            "outputGroups":[
               {
                  "customName":"test",
                  "name":"DASH ISO",
                  "outputs":[
                     {
                        "containerSettings":{
                           "container":"MPD"
                        },
                        "videoDescription":{
                           "scalingBehavior":"DEFAULT",
                           "timecodeInsertion":"DISABLED",
                           "antiAlias":"ENABLED",
                           "sharpness":50,
                           "codecSettings":{
                              "codec":"H_264",
                              "h264Settings":{
                                 "interlaceMode":"PROGRESSIVE",
                                 "numberReferenceFrames":1,
                                 "syntax":"DEFAULT",
                                 "softness":0,
                                 "gopClosedCadence":1,
                                 "gopSize":90.0,
                                 "slices":1,
                                 "gopBReference":"DISABLED",
                                 "slowPal":"DISABLED",
                                 "spatialAdaptiveQuantization":"ENABLED",
                                 "temporalAdaptiveQuantization":"ENABLED",
                                 "flickerAdaptiveQuantization":"ENABLED",
                                 "entropyEncoding":"CABAC",
                                 "bitrate":5000000,
                                 "framerateControl":"INITIALIZE_FROM_SOURCE",
                                 "rateControlMode":"CBR",
                                 "codecProfile":"MAIN",
                                 "telecine":"NONE",
                                 "minIInterval":0,
                                 "adaptiveQuantization":"MEDIUM",
                                 "codecLevel":"AUTO",
                                 "fieldEncoding":"PAFF",
                                 "sceneChangeDetect":"ENABLED",
                                 "qualityTuningLevel":"SINGLE_PASS",
                                 "framerateConversionAlgorithm":"DUPLICATE_DROP",
                                 "unregisteredSeiTimecode":"DISABLED",
                                 "gopSizeUnits":"FRAMES",
                                 "parControl":"INITIALIZE_FROM_SOURCE",
                                 "numberBFramesBetweenReferenceFrames":2,
                                 "repeatPps":"DISABLED"
                              }
                           },
                           "afdSignaling":"NONE",
                           "dropFrameTimecode":"ENABLED",
                           "respondToAfd":"NONE",
                           "colorMetadata":"INSERT"
                        },
                        "audioDescriptions":[
                           {
                              "audioTypeControl":"FOLLOW_INPUT",
                              "codecSettings":{
                                 "codec":"AAC",
                                 "aacSettings":{
                                    "audioDescriptionBroadcasterMix":"NORMAL",
                                    "bitrate":96000,
                                    "rateControlMode":"CBR",
                                    "codecProfile":"LC",
                                    "codingMode":"CODING_MODE_2_0",
                                    "rawFormat":"NONE",
                                    "sampleRate":48000,
                                    "specification":"MPEG4"
                                 }
                              },
                              "languageCodeControl":"FOLLOW_INPUT"
                           }
                        ],
                        "nameModifier":"aaa"
                     }
                  ],
                  "outputGroupSettings":{
                     "type":"DASH_ISO_GROUP_SETTINGS",
                     "dashIsoGroupSettings":{
                        "segmentLength":30,
                        "destination":"s3://mediaconvert-testuser/clip01.mp4",
                        "encryption":"***",
                        "fragmentLength":2,
                        "segmentControl":"SINGLE_FILE",
                        "hbbtvCompliance":"NONE"
                     }
                  }
               }
            ],
            "adAvailOffset":0,
            "inputs":[
               {
                  "audioSelectors":{
                     "Audio Selector 1":{
                        "offset":0,
                        "defaultSelection":"DEFAULT",
                        "programSelection":1
                     }
                  },
                  "videoSelector":{
                     "colorSpace":"FOLLOW"
                  },
                  "filterEnable":"AUTO",
                  "psiControl":"USE_PSI",
                  "filterStrength":0,
                  "deblockFilter":"DISABLED",
                  "denoiseFilter":"DISABLED",
                  "timecodeSource":"EMBEDDED",
                  "fileInput":"s3://mediaconvert-testuser/clip01.mp4"
               }
            ]
         },
         "status":"SUBMITTED",
         "timing":{
            "submitTime":"1510714652428"
         }
      }
   },
   "requestID":"b99d731e-c9b0-11e7-9b04-7fc9a0800896",
   "eventID":"22ef8e82-ea2c-4014-9a45-16fd11474b31",
   "readOnly":false,
   "eventType":"AwsApiCall",
   "recipientAccountId":"123456789000"
}
```