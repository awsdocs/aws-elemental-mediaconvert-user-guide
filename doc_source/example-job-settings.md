# Example AWS Elemental MediaConvert job settings in JSON<a name="example-job-settings"></a>

The job settings in these examples represent the simplest valid jobs you can run\. They work well for experimenting with the service\. When you want to perform more complex transcodes or create different outputs, use the console to set up your job and to generate your JSON job specification\. To do so, in the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)

**Important**  
We recommend that you use the MediaConvert console to generate your production JSON job specification\.  
Your job specification must conform to validation by the transcoding engine\. The transcoding engine validations represent complex dependencies among groups of settings and dependencies between your transcoding settings and properties of your input files\. The MediaConvert console functions as an interactive job builder to make it easy to create valid job JSON specifications\. You can use [job templates](using-a-job-template.md) and [output presets](using-a-preset-to-specify-a-job-output.md) to get started quickly\.

To use these examples, replace the following placeholder values with actual values:
+ ROLE HERE
+ s3://INPUT HERE
+ s3://OUTPUT HERE

**Topics**
+ [Example—mp4 output](#mp4-example)
+ [Example—ABR output](#HLS-ABR-example)

## Example—mp4 output<a name="mp4-example"></a>

```
{
  "UserMetadata": {},
  "Role": "ROLE ARN",
  "Settings": {
    "OutputGroups": [
      {
        "Name": "File Group",
        "OutputGroupSettings": {
          "Type": "FILE_GROUP_SETTINGS",
          "FileGroupSettings": {
            "Destination": "s3://bucket/out"
          }
        },
        "Outputs": [
          {
            "VideoDescription": {
              "ScalingBehavior": "DEFAULT",
              "TimecodeInsertion": "DISABLED",
              "AntiAlias": "ENABLED",
              "Sharpness": 50,
              "CodecSettings": {
                "Codec": "H_264",
                "H264Settings": {
                  "InterlaceMode": "PROGRESSIVE",
                  "NumberReferenceFrames": 3,
                  "Syntax": "DEFAULT",
                  "Softness": 0,
                  "GopClosedCadence": 1,
                  "GopSize": 48,
                  "Slices": 1,
                  "GopBReference": "DISABLED",
                  "SlowPal": "DISABLED",
                  "SpatialAdaptiveQuantization": "ENABLED",
                  "TemporalAdaptiveQuantization": "ENABLED",
                  "FlickerAdaptiveQuantization": "DISABLED",
                  "EntropyEncoding": "CABAC",
                  "Bitrate": 4500000,
                  "FramerateControl": "SPECIFIED",
                  "RateControlMode": "CBR",
                  "CodecProfile": "HIGH",
                  "Telecine": "NONE",
                  "MinIInterval": 0,
                  "AdaptiveQuantization": "HIGH",
                  "CodecLevel": "LEVEL_4_1",
                  "FieldEncoding": "PAFF",
                  "SceneChangeDetect": "ENABLED",
                  "QualityTuningLevel": "SINGLE_PASS_HQ",
                  "FramerateConversionAlgorithm": "DUPLICATE_DROP",
                  "UnregisteredSeiTimecode": "DISABLED",
                  "GopSizeUnits": "FRAMES",
                  "ParControl": "INITIALIZE_FROM_SOURCE",
                  "NumberBFramesBetweenReferenceFrames": 3,
                  "RepeatPps": "DISABLED",
                  "HrdBufferSize": 9000000,
                  "HrdBufferInitialFillPercentage": 90,
                  "FramerateNumerator": 24000,
                  "FramerateDenominator": 1001
                }
              },
              "AfdSignaling": "NONE",
              "DropFrameTimecode": "ENABLED",
              "RespondToAfd": "NONE",
              "ColorMetadata": "INSERT",
              "Width": 1920,
              "Height": 1080
            },
            "AudioDescriptions": [
              {
                "AudioTypeControl": "FOLLOW_INPUT",
                "CodecSettings": {
                  "Codec": "AAC",
                  "AacSettings": {
                    "AudioDescriptionBroadcasterMix": "NORMAL",
                    "Bitrate": 96000,
                    "RateControlMode": "CBR",
                    "CodecProfile": "LC",
                    "CodingMode": "CODING_MODE_2_0",
                    "RawFormat": "NONE",
                    "SampleRate": 48000,
                    "Specification": "MPEG4"
                  }
                },
                "LanguageCodeControl": "FOLLOW_INPUT"
              }
            ],
            "ContainerSettings": {
              "Container": "MP4",
              "Mp4Settings": {
                "CslgAtom": "INCLUDE",
                "FreeSpaceBox": "EXCLUDE",
                "MoovPlacement": "PROGRESSIVE_DOWNLOAD"
              }
            }
          }
        ]
      }
    ],
    "AdAvailOffset": 0,
    "Inputs": [
      {
        "AudioSelectors": {
          "Audio Selector 1": {
            "Tracks": [
              1
            ],
            "Offset": 0,
            "DefaultSelection": "DEFAULT",
            "SelectorType": "TRACK",
            "ProgramSelection": 1
          },
          "Audio Selector 2": {
            "Tracks": [
              2
            ],
            "Offset": 0,
            "DefaultSelection": "NOT_DEFAULT",
            "SelectorType": "TRACK",
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
        "TimecodeSource": "EMBEDDED",
        "FileInput": "s3://input"
      }
    ]
  }
}
```

## Example—ABR output<a name="HLS-ABR-example"></a>

```
{
  "UserMetadata": {},
  "Role": "ROLE ARN",
  "Settings": {
    "OutputGroups": [
      {
        "Name": "Apple HLS",
        "Outputs": [
          {
            "ContainerSettings": {
              "Container": "M3U8",
              "M3u8Settings": {
                "AudioFramesPerPes": 2,
                "PcrControl": "PCR_EVERY_PES_PACKET",
                "PmtPid": 480,
                "PrivateMetadataPid": 503,
                "ProgramNumber": 1,
                "PatInterval": 100,
                "PmtInterval": 100,
                "VideoPid": 481,
                "AudioPids": [
                  482,
                  483,
                  484,
                  485,
                  486,
                  487,
                  488,
                  489,
                  490,
                  491,
                  492
                ]
              }
            },
            "VideoDescription": {
              "Width": 1920,
              "Height": 1080,
              "VideoPreprocessors": {
                "Deinterlacer": {
                  "Algorithm": "INTERPOLATE",
                  "Mode": "DEINTERLACE"
                }
              },
              "AntiAlias": "ENABLED",
              "Sharpness": 100,
              "CodecSettings": {
                "Codec": "H_264",
                "H264Settings": {
                  "InterlaceMode": "PROGRESSIVE",
                  "ParNumerator": 1,
                  "NumberReferenceFrames": 3,
                  "Softness": 0,
                  "FramerateDenominator": 1001,
                  "GopClosedCadence": 1,
                  "GopSize": 90,
                  "Slices": 1,
                  "HrdBufferSize": 12500000,
                  "ParDenominator": 1,
                  "SpatialAdaptiveQuantization": "ENABLED",
                  "TemporalAdaptiveQuantization": "DISABLED",
                  "FlickerAdaptiveQuantization": "DISABLED",
                  "EntropyEncoding": "CABAC",
                  "Bitrate": 8500000,
                  "FramerateControl": "SPECIFIED",
                  "RateControlMode": "CBR",
                  "CodecProfile": "HIGH",
                  "Telecine": "NONE",
                  "FramerateNumerator": 30000,
                  "MinIInterval": 0,
                  "AdaptiveQuantization": "MEDIUM",
                  "CodecLevel": "LEVEL_4",
                  "SceneChangeDetect": "ENABLED",
                  "QualityTuningLevel": "SINGLE_PASS_HQ",
                  "GopSizeUnits": "FRAMES",
                  "ParControl": "SPECIFIED",
                  "NumberBFramesBetweenReferenceFrames": 3,
                  "HrdBufferInitialFillPercentage": 90,
                  "Syntax": "DEFAULT"
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
                "AudioSourceName": "Audio Selector 1",
                "CodecSettings": {
                  "Codec": "AAC",
                  "AacSettings": {
                    "Bitrate": 128000,
                    "RateControlMode": "CBR",
                    "CodecProfile": "LC",
                    "CodingMode": "CODING_MODE_2_0",
                    "SampleRate": 48000
                  }
                },
                "LanguageCodeControl": "FOLLOW_INPUT"
              }
            ],
            "NameModifier": "_high"
          },
          {
            "VideoDescription": {
              "ScalingBehavior": "DEFAULT",
              "TimecodeInsertion": "DISABLED",
              "AntiAlias": "ENABLED",
              "Sharpness": 50,
              "CodecSettings": {
                "Codec": "H_264",
                "H264Settings": {
                  "InterlaceMode": "PROGRESSIVE",
                  "NumberReferenceFrames": 3,
                  "Syntax": "DEFAULT",
                  "Softness": 0,
                  "GopClosedCadence": 1,
                  "GopSize": 90,
                  "Slices": 1,
                  "GopBReference": "DISABLED",
                  "SlowPal": "DISABLED",
                  "SpatialAdaptiveQuantization": "ENABLED",
                  "TemporalAdaptiveQuantization": "ENABLED",
                  "FlickerAdaptiveQuantization": "DISABLED",
                  "EntropyEncoding": "CABAC",
                  "Bitrate": 7500000,
                  "FramerateControl": "INITIALIZE_FROM_SOURCE",
                  "RateControlMode": "CBR",
                  "CodecProfile": "MAIN",
                  "Telecine": "NONE",
                  "MinIInterval": 0,
                  "AdaptiveQuantization": "HIGH",
                  "CodecLevel": "AUTO",
                  "FieldEncoding": "PAFF",
                  "SceneChangeDetect": "ENABLED",
                  "QualityTuningLevel": "SINGLE_PASS",
                  "FramerateConversionAlgorithm": "DUPLICATE_DROP",
                  "UnregisteredSeiTimecode": "DISABLED",
                  "GopSizeUnits": "FRAMES",
                  "ParControl": "INITIALIZE_FROM_SOURCE",
                  "NumberBFramesBetweenReferenceFrames": 2,
                  "RepeatPps": "DISABLED"
                }
              },
              "AfdSignaling": "NONE",
              "DropFrameTimecode": "ENABLED",
              "RespondToAfd": "NONE",
              "ColorMetadata": "INSERT",
              "Width": 1280,
              "Height": 720
            },
            "AudioDescriptions": [
              {
                "AudioTypeControl": "FOLLOW_INPUT",
                "CodecSettings": {
                  "Codec": "AAC",
                  "AacSettings": {
                    "AudioDescriptionBroadcasterMix": "NORMAL",
                    "Bitrate": 96000,
                    "RateControlMode": "CBR",
                    "CodecProfile": "LC",
                    "CodingMode": "CODING_MODE_2_0",
                    "RawFormat": "NONE",
                    "SampleRate": 48000,
                    "Specification": "MPEG4"
                  }
                },
                "LanguageCodeControl": "FOLLOW_INPUT"
              }
            ],
            "OutputSettings": {
              "HlsSettings": {
                "AudioGroupId": "program_audio",
                "AudioRenditionSets": "program_audio",
                "IFrameOnlyManifest": "EXCLUDE"
              }
            },
            "ContainerSettings": {
              "Container": "M3U8",
              "M3u8Settings": {
                "AudioFramesPerPes": 4,
                "PcrControl": "PCR_EVERY_PES_PACKET",
                "PmtPid": 480,
                "PrivateMetadataPid": 503,
                "ProgramNumber": 1,
                "PatInterval": 0,
                "PmtInterval": 0,
                "Scte35Source": "NONE",
                "Scte35Pid": 500,
                "TimedMetadata": "NONE",
                "TimedMetadataPid": 502,
                "VideoPid": 481,
                "AudioPids": [
                  482,
                  483,
                  484,
                  485,
                  486,
                  487,
                  488,
                  489,
                  490,
                  491,
                  492
                ]
              }
            },
            "NameModifier": "_med"
          },
          {
            "VideoDescription": {
              "ScalingBehavior": "DEFAULT",
              "TimecodeInsertion": "DISABLED",
              "AntiAlias": "ENABLED",
              "Sharpness": 100,
              "CodecSettings": {
                "Codec": "H_264",
                "H264Settings": {
                  "InterlaceMode": "PROGRESSIVE",
                  "NumberReferenceFrames": 3,
                  "Syntax": "DEFAULT",
                  "Softness": 0,
                  "GopClosedCadence": 1,
                  "GopSize": 90,
                  "Slices": 1,
                  "GopBReference": "DISABLED",
                  "SlowPal": "DISABLED",
                  "SpatialAdaptiveQuantization": "ENABLED",
                  "TemporalAdaptiveQuantization": "ENABLED",
                  "FlickerAdaptiveQuantization": "DISABLED",
                  "EntropyEncoding": "CABAC",
                  "Bitrate": 3500000,
                  "FramerateControl": "INITIALIZE_FROM_SOURCE",
                  "RateControlMode": "CBR",
                  "CodecProfile": "MAIN",
                  "Telecine": "NONE",
                  "MinIInterval": 0,
                  "AdaptiveQuantization": "HIGH",
                  "CodecLevel": "LEVEL_3_1",
                  "FieldEncoding": "PAFF",
                  "SceneChangeDetect": "ENABLED",
                  "QualityTuningLevel": "SINGLE_PASS_HQ",
                  "FramerateConversionAlgorithm": "DUPLICATE_DROP",
                  "UnregisteredSeiTimecode": "DISABLED",
                  "GopSizeUnits": "FRAMES",
                  "ParControl": "INITIALIZE_FROM_SOURCE",
                  "NumberBFramesBetweenReferenceFrames": 2,
                  "RepeatPps": "DISABLED"
                }
              },
              "AfdSignaling": "NONE",
              "DropFrameTimecode": "ENABLED",
              "RespondToAfd": "NONE",
              "ColorMetadata": "INSERT",
              "Width": 960,
              "Height": 540
            },
            "AudioDescriptions": [
              {
                "AudioTypeControl": "FOLLOW_INPUT",
                "CodecSettings": {
                  "Codec": "AAC",
                  "AacSettings": {
                    "AudioDescriptionBroadcasterMix": "NORMAL",
                    "Bitrate": 96000,
                    "RateControlMode": "CBR",
                    "CodecProfile": "LC",
                    "CodingMode": "CODING_MODE_2_0",
                    "RawFormat": "NONE",
                    "SampleRate": 48000,
                    "Specification": "MPEG4"
                  }
                },
                "LanguageCodeControl": "FOLLOW_INPUT"
              }
            ],
            "OutputSettings": {
              "HlsSettings": {
                "AudioGroupId": "program_audio",
                "AudioRenditionSets": "program_audio",
                "IFrameOnlyManifest": "EXCLUDE"
              }
            },
            "ContainerSettings": {
              "Container": "M3U8",
              "M3u8Settings": {
                "AudioFramesPerPes": 4,
                "PcrControl": "PCR_EVERY_PES_PACKET",
                "PmtPid": 480,
                "PrivateMetadataPid": 503,
                "ProgramNumber": 1,
                "PatInterval": 0,
                "PmtInterval": 0,
                "Scte35Source": "NONE",
                "Scte35Pid": 500,
                "TimedMetadata": "NONE",
                "TimedMetadataPid": 502,
                "VideoPid": 481,
                "AudioPids": [
                  482,
                  483,
                  484,
                  485,
                  486,
                  487,
                  488,
                  489,
                  490,
                  491,
                  492
                ]
              }
            },
            "NameModifier": "_low"
          }
        ],
        "OutputGroupSettings": {
          "Type": "HLS_GROUP_SETTINGS",
          "HlsGroupSettings": {
            "ManifestDurationFormat": "INTEGER",
            "SegmentLength": 10,
            "TimedMetadataId3Period": 10,
            "CaptionLanguageSetting": "OMIT",
            "Destination": "s3://bucket/hls1/master",
            "TimedMetadataId3Frame": "PRIV",
            "CodecSpecification": "RFC_4281",
            "OutputSelection": "MANIFESTS_AND_SEGMENTS",
            "ProgramDateTimePeriod": 600,
            "MinSegmentLength": 0,
            "DirectoryStructure": "SINGLE_DIRECTORY",
            "ProgramDateTime": "EXCLUDE",
            "SegmentControl": "SEGMENTED_FILES",
            "ManifestCompression": "NONE",
            "ClientCache": "ENABLED",
            "StreamInfResolution": "INCLUDE"
          }
        }
      }
    ],
    "AdAvailOffset": 0,
    "Inputs": [
      {
        "AudioSelectors": {
          "Audio Selector 1": {
            "Tracks": [
              1
            ],
            "Offset": 0,
            "DefaultSelection": "DEFAULT",
            "SelectorType": "TRACK",
            "ProgramSelection": 1
          },
          "Audio Selector 2": {
            "Tracks": [
              2
            ],
            "Offset": 0,
            "DefaultSelection": "NOT_DEFAULT",
            "SelectorType": "TRACK",
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
        "TimecodeSource": "EMBEDDED",
        "FileInput": "s3://INPUT"
      }
    ]
  }
}
```