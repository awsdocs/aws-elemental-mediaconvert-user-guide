# Example accelerated transcoding JSON job for AWS Elemental MediaConvert<a name="sample-acceleration-job-settings-in-json"></a>

The following example JSON job converts an MP4 file to another MP4 file that is 720p encoded with H\.265\. To use this example, replace the settings with your values\. At minimum, you must provide values for the following settings:
+ `Role`: This is the AWS Identity and Access Management \(IAM\) role that you set up to give AWS Elemental MediaConvert permission to access your input and output Amazon S3 buckets and to access Amazon API Gateway on your behalf\. For information about setting up this role, see [Set up IAM permissions](https://docs.aws.amazon.com/mediaconvert/latest/ug/iam-role.html) in the *AWS Elemental MediaConvert User Guide*\.
+ `Destination`: The Amazon S3 bucket where you want MediaConvert to store your output file\. Make sure to include a trailing backslash, as in the example\.
+ `InputClippings`: Define the clips that you want transcoded by specifying sets of values for `StartTimecode` and `EndTimecode`\. Alternatively, you can remove `InputClippings` entirely to transcode the entire asset\.
+ **`FileInput`**: Specify the file name and location for your input file\. Your file input can be an Amazon S3 object or an HTTP URL\.

  Accelerated transcoding is supported with jobs that have only a single input; you can't do input stitching\.

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