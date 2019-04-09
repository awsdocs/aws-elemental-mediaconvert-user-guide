# Using Accelerated Transcoding in AWS Elemental MediaConvert<a name="accelerated-transcoding"></a>

AWS Elemental MediaConvert jobs that create premium content, such as those that incorporate Ultra High Definition \(UHD\) and High Dynamic Range \(HDR\) content, can have high computational requirements and can take longer to complete\. To reduce the transcoding time required to run these jobs, you can use accelerated transcoding\. Consider using accelerated transcoding for jobs that would otherwise take 10 minutes or longer to run\.

For example, jobs that generate the following assets might benefit from accelerated transcoding:
+ Ultra High Definition content
+ High dynamic range content in HEVC
+ Any long\-duration, visually complex video

**Note**  
Accelerated transcoding is a Professional tier feature\. You pay more per minute of transcoded output for outputs that use Professional tier features\. For more information about MediaConvert pricing tiers, see [MediaConvert Pricing](https://aws.amazon.com/mediaconvert/pricing/)\.

## Setting Up Accelerated Transcoding in AWS Elemental MediaConvert<a name="setting-up-accelerated-transcoding"></a>

You set up accelerated transcoding for your AWS Elemental MediaConvert jobs in the same way that you set up unaccelerated jobs, except that you enable acceleration\.

**Note**  
We recommend that you use a dedicated transcoding queue for your accelerated transcoding jobs, to provide isolation between the resources that you use for your accelerated jobs and your other jobs\.

**To set up your transcoding job with accelerated transcoding \(console\)**

1. Set up your transcoding job as usual\. For more information, see [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

   Make sure that your job input files and output settings conform to the limitations and requirements listed in [Job Limitations and Requirements for Accelerated Transcoding in AWS Elemental MediaConvert](#job-requirements)\.

1. Change your timecode settings from the default value **Embedded** to **Start at zero**\.

   1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

   1. In the **Timecode configuration** pane, for **Source**, choose **Start at 0**\.

   1. On the **Create job** page, in the **Job** pane on the left, under **Inputs**, choose the input\.

   1. In the **Video selector ** pane, for **Timecode source**, choose **Start at 0**\.

1. If you don't already have a dedicated queue for accelerated transcoding jobs, create one\. For more information, see [Creating an On\-Demand Queue in AWS Elemental MediaConvert](creating-queues.md)\.\.

1. On the **Create job** page, in the **Job** pane on the left, in the **Job Settings** section, choose **Settings**\.

1. For **Acceleration**, choose **Enabled**\.

If you use the API or an SDK, you can find this setting in the JSON file of your job, called [AccelerationSettings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-job-accelerationsettings)\.

## Example Accelerated Transcoding Job for AWS Elemental MediaConvert<a name="sample-acceleration-job-settings-in-json"></a>

The following example JSON job specification converts an MP4 file to another MP4 file that is 720p encoded with H\.265\. To use this example, replace the settings with your values\. At minimum, you must provide values for the following settings:
+ `Role`: This is the AWS Identity and Access Management \(IAM\) role that you set up to give AWS Elemental MediaConvert permission to access your input and output Amazon S3 buckets and to access Amazon API Gateway on your behalf\. For information about setting up this role, see [Set Up IAM Permissions](https://docs.aws.amazon.com/mediaconvert/latest/ug/iam-role.html) in the *AWS Elemental MediaConvert User Guide*\.
+ `Destination`: The Amazon S3 bucket where you want MediaConvert to store your output file\. Make sure to include a trailing backslash, as in the example\.
+ `InputClippings`: Define the clips that you want transcoded by specifying sets of values for `StartTimecode` and `EndTimecode`\. Alternatively, you can remove `InputClippings` entirely to transcode the entire asset\.
+ **`FileInput`**: Specify the file name and location in Amazon S3 for your input file\. Accelerated transcoding is supported with jobs that have only a single input; you can't do input stitching\.

```
{
  "Role": "arn:aws:iam::123456789012:role/MediaConvert_Role",
  "AccelerationSettings" : {
    "Mode" : "ENABLED"
  },
  "UserMetadata": {
      "job" : "Acceleration"
  },
  "Settings": {
    "TimecodeConfig": {
      "Source": "ZEROBASED"
    },
    "OutputGroups": [
      {
        "Name": "File Group",
        "Outputs": [
          {
            "ContainerSettings": {
              "Container": "MP4",
              "Mp4Settings": {
                "CslgAtom": "EXCLUDE",
                "FreeSpaceBox": "EXCLUDE",
                "MoovPlacement": "NORMAL"
              }
            },
            "VideoDescription": {
              "Width": 1280,
              "ScalingBehavior": "DEFAULT",
              "Height": 720,
              "VideoPreprocessors": {
                "TimecodeBurnin": {
                  "FontSize": 32,
                  "Position": "TOP_CENTER"
                }
              },
              "TimecodeInsertion": "DISABLED",
              "AntiAlias": "ENABLED",
              "Sharpness": 50,
              "CodecSettings": {
                "Codec": "H_265",
                "H265Settings": {
                  "InterlaceMode": "PROGRESSIVE",
                  "ParNumerator": 1,
                  "NumberReferenceFrames": 3,
                  "FramerateDenominator": 1001,
                  "GopClosedCadence": 1,
                  "AlternateTransferFunctionSei": "DISABLED",
                  "HrdBufferInitialFillPercentage": 90,
                  "GopSize": 48,
                  "Slices": 4,
                  "GopBReference": "ENABLED",
                  "HrdBufferSize": 20000000,
                  "SlowPal": "DISABLED",
                  "ParDenominator": 1,
                  "SpatialAdaptiveQuantization": "ENABLED",
                  "TemporalAdaptiveQuantization": "ENABLED",
                  "FlickerAdaptiveQuantization": "DISABLED",
                  "Bitrate": 10000000,
                  "FramerateControl": "INITIALIZE_FROM_SOURCE",
                  "RateControlMode": "CBR",
                  "CodecProfile": "MAIN_MAIN",
                  "Tiles": "ENABLED",
                  "Telecine": "NONE",
                  "FramerateNumerator": 24000,
                  "MinIInterval": 0,
                  "AdaptiveQuantization": "HIGH",
                  "CodecLevel": "LEVEL_5",
                  "SceneChangeDetect": "ENABLED",
                  "QualityTuningLevel": "SINGLE_PASS_HQ",
                  "FramerateConversionAlgorithm": "DUPLICATE_DROP",
                  "UnregisteredSeiTimecode": "DISABLED",
                  "GopSizeUnits": "FRAMES",
                  "ParControl": "SPECIFIED",
                  "NumberBFramesBetweenReferenceFrames": 3,
                  "TemporalIds": "DISABLED",
                  "SampleAdaptiveOffsetFilterMode": "ADAPTIVE"
                }
              },
              "AfdSignaling": "NONE",
              "DropFrameTimecode": "ENABLED",
              "RespondToAfd": "NONE",
              "ColorMetadata": "INSERT"
            },
            "AudioDescriptions": [
              {
                "AudioTypeControl": "FOLLOW_INPUT",
                "CodecSettings": {
                  "Codec": "AAC",
                  "AacSettings": {
                    "AudioDescriptionBroadcasterMix": "NORMAL",
                    "Bitrate": 160000,
                    "RateControlMode": "CBR",
                    "CodecProfile": "LC",
                    "CodingMode": "CODING_MODE_2_0",
                    "RawFormat": "NONE",
                    "SampleRate": 48000,
                    "Specification": "MPEG4"
                  }
                },
                "LanguageCodeControl": "FOLLOW_INPUT",
                "AudioType": 0
              }
            ],
            "Extension": "mp4",
            "NameModifier": "1280x720"
          }
        ],
        "OutputGroupSettings": {
          "Type": "FILE_GROUP_SETTINGS",
          "FileGroupSettings": {
            "Destination": "s3://mediaconvert-outputs/accelerated/"
          }
        }
      }
    ],
    "AdAvailOffset": 0,
    "Inputs": [
      {
        "InputClippings": [
          {
            "EndTimecode": "01:00:00:00",
            "StartTimecode": "00:00:00:00"
          }
        ],
        "AudioSelectors": {
          "Audio Selector 1": {
            "Offset": 0,
            "DefaultSelection": "DEFAULT",
            "ProgramSelection": 1
          }
        },
        "VideoSelector": {
          "ColorSpace": "FOLLOW"
        },
        "FilterEnable": "AUTO",
        "PsiControl": "USE_PSI",
        "FilterStrength": 0,
        "DeblockFilter": "DISABLED",
        "DenoiseFilter": "DISABLED",
        "TimecodeSource": "ZEROBASED",
        "FileInput": "s3://mediaconvert-inputs/SampleVideo_h264_StereoAudio.mp4"
      }
    ]
  }
}
```

## Job Limitations and Requirements for Accelerated Transcoding in AWS Elemental MediaConvert<a name="job-requirements"></a>

Before you enable accelerated transcoding, make sure that your job conforms to the following requirements and limitations\.

**Video Input Requirements**
+ Maximum inputs: 1
+ Progressive scan type only\. Telecine input is not supported\.
+ The following table shows the supported video input codecs and containers\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/accelerated-transcoding.html)

**Output Restrictions**
+ You can't set up an output for frame capture\. That is, you can't choose **Frame Capture to JPEG** for **Video codec** in any of your outputs\.
+ Use only supported combinations of container and codec\. The following table shows the supported video output codecs and containers\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/accelerated-transcoding.html)
**Note**  
For MPEG\-2 TS outputs, to use accelerated transcoding, you must change the default value of **CBR** for **Transport stream settings** > **Rate mode** to **VBR**\.
+ Use only supported output captions formats\. You can use the following output captions types with unaccelerated jobs, but you can't use them with accelerated transcoding:
  + Burn\-in
  + SCTE\-20

**Transcoding Features Not Supported with Accelerated Transcoding**
+ Slow PAL
+ Watermarking
+ Avail blanking
+ Motion image inserter \(Motion graphic overlay\)
+ Interpolated frame rate conversion
+ Frame capture to JPEG
+ VBI passthrough
+ Timecode passthrough
+ SEI timecode
+ Timecode anchor
+ Telecine output
+ Inverse telecine output
+ Open GOP outputs
+ Embedded timecode source
**Note**  
With accelerated transcoding, you can set the input setting **Timecode source** to **Embedded**, but not the job\-wide setting **Source** under **Timecode configuration**\.
+ Values for Min\-I interval other than the default of 0
+ ESAM
+ SCTE\-35 passthrough