# AWS Elemental MediaConvert postman collection files<a name="postman-collection-files"></a>

Use these collections with Postman for simple access to MediaConvert through the REST API\. Copy the collections and save them as JSON files, then import them into Postman\.

**Topics**
+ [MediaConvert list resources collection](#postman-collection-GET)
+ [MediaConvert create resources collection](#postman-collection-POST)
+ [MediaConvert resource tagging collection](#tagging-collection)

## MediaConvert list resources collection<a name="postman-collection-GET"></a>

```
{
	"id": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
	"name": "AWS Elemental MediaConvert GET Request",
	"description": "AWS Elemental MediaConvert GET Request",
	"order": [
		"bc671df5-4a85-54b6-f137-19cb70516fd2",
		"85318a0b-c490-3718-62eb-2a737de83af0",
		"1fd40def-ca4b-1842-c99a-778f62269010",
		"8c5ee49e-3eb0-5b9f-ae03-f6ce59763c93",
		"abedbb9c-4b97-6596-ae4c-dc1ff83f1e59",
		"0348eabe-0893-696e-718d-e819e699b34c"
	],
	"folders": [],
	"folders_order": [],
	"timestamp": 0,
	"owner": "2332976",
	"public": false,
	"requests": [
		{
			"id": "0348eabe-0893-696e-718d-e819e699b34c",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/presets/<name-of-preset>",
			"folder": null,
			"queryParams": [],
			"preRequestScript": null,
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": null,
			"dataMode": "params",
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530559387196,
			"name": "List of Job Presets",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		},
		{
			"id": "1fd40def-ca4b-1842-c99a-778f62269010",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/queues",
			"folder": null,
			"queryParams": [],
			"preRequestScript": null,
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": null,
			"dataMode": "params",
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530558971036,
			"name": "List All Queues",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		},
		{
			"id": "85318a0b-c490-3718-62eb-2a737de83af0",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/queues/<QUEUE-NAME-HERE>",
			"folder": null,
			"queryParams": [],
			"preRequestScript": null,
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": null,
			"dataMode": "params",
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530558975692,
			"name": "Specific Queue Details",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		},
		{
			"id": "8c5ee49e-3eb0-5b9f-ae03-f6ce59763c93",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobTemplates/<job-template-name>",
			"folder": null,
			"queryParams": [],
			"preRequestScript": null,
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": null,
			"dataMode": "params",
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530559427717,
			"name": "Specific Job Template",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		},
		{
			"id": "abedbb9c-4b97-6596-ae4c-dc1ff83f1e59",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobTemplates",
			"queryParams": [],
			"pathVariables": {},
			"pathVariableData": [],
			"preRequestScript": null,
			"method": "GET",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"data": null,
			"dataMode": "params",
			"name": "List of Job Templates",
			"description": "",
			"descriptionFormat": "html",
			"time": 1530559135843,
			"version": 2,
			"responses": [],
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			}
		},
		{
			"id": "bc671df5-4a85-54b6-f137-19cb70516fd2",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobs/<job-id>",
			"folder": null,
			"queryParams": [],
			"preRequestScript": null,
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": null,
			"dataMode": "params",
			"tests": null,
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530558979699,
			"name": "Specific Job ID",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		}
	]
}
```

## MediaConvert create resources collection<a name="postman-collection-POST"></a>

```
{
	"id": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
	"name": "AWS Elemental MediaConvert POST Request",
	"description": "",
	"order": [
		"18510e9e-cc88-8c19-5b28-64606a24bb03",
		"b4a440ea-e235-fefa-636f-d0f5da8143f5",
		"dbad1515-df7d-fbc7-84ad-bd97688ee0dd",
		"37896178-5574-1b03-858f-8c3dd362c231",
		"3a124a9e-e437-2a47-b8e1-eb51e121311c"
	],
	"folders": [],
	"folders_order": [],
	"timestamp": 0,
	"owner": "2332976",
	"public": false,
	"requests": [
		{
			"id": "18510e9e-cc88-8c19-5b28-64606a24bb03",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobs",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530561471298,
			"name": "Submit MP4 Job (No Preset)",
			"description": "",
			"collectionId": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
			"responses": [],
			"rawModeData": "{\r\n  \"userMetadata\": {},\r\n  \"role\": \"ROLE ARN HERE\",\r\n  \"settings\": {\r\n    \"outputGroups\": [\r\n      {\r\n        \"name\": \"File Group\",\r\n        \"outputs\": [\r\n          {\r\n            \"containerSettings\": {\r\n              \"container\": \"MP4\",\r\n              \"mp4Settings\": {\r\n                \"cslgAtom\": \"INCLUDE\",\r\n                \"freeSpaceBox\": \"EXCLUDE\",\r\n                \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\r\n              }\r\n            },\r\n            \"videoDescription\": {\r\n              \"scalingBehavior\": \"DEFAULT\",\r\n              \"timecodeInsertion\": \"DISABLED\",\r\n              \"antiAlias\": \"ENABLED\",\r\n              \"sharpness\": 50,\r\n              \"codecSettings\": {\r\n                \"codec\": \"H_264\",\r\n                \"h264Settings\": {\r\n                  \"interlaceMode\": \"PROGRESSIVE\",\r\n                  \"numberReferenceFrames\": 1,\r\n                  \"syntax\": \"DEFAULT\",\r\n                  \"softness\": 0,\r\n                  \"gopClosedCadence\": 1,\r\n                  \"gopSize\": 90,\r\n                  \"slices\": 1,\r\n                  \"gopBReference\": \"DISABLED\",\r\n                  \"slowPal\": \"DISABLED\",\r\n                  \"spatialAdaptiveQuantization\": \"ENABLED\",\r\n                  \"temporalAdaptiveQuantization\": \"ENABLED\",\r\n                  \"flickerAdaptiveQuantization\": \"ENABLED\",\r\n                  \"entropyEncoding\": \"CABAC\",\r\n                  \"bitrate\": 5000000,\r\n                  \"framerateControl\": \"INITIALIZE_FROM_SOURCE\",\r\n                  \"rateControlMode\": \"CBR\",\r\n                  \"codecProfile\": \"MAIN\",\r\n                  \"telecine\": \"NONE\",\r\n                  \"minIInterval\": 0,\r\n                  \"adaptiveQuantization\": \"MEDIUM\",\r\n                  \"codecLevel\": \"AUTO\",\r\n                  \"fieldEncoding\": \"PAFF\",\r\n                  \"sceneChangeDetect\": \"ENABLED\",\r\n                  \"qualityTuningLevel\": \"SINGLE_PASS\",\r\n                  \"framerateConversionAlgorithm\": \"DUPLICATE_DROP\",\r\n                  \"unregisteredSeiTimecode\": \"DISABLED\",\r\n                  \"gopSizeUnits\": \"FRAMES\",\r\n                  \"parControl\": \"INITIALIZE_FROM_SOURCE\",\r\n                  \"numberBFramesBetweenReferenceFrames\": 2,\r\n                  \"repeatPps\": \"DISABLED\"\r\n                }\r\n              },\r\n              \"afdSignaling\": \"NONE\",\r\n              \"dropFrameTimecode\": \"ENABLED\",\r\n              \"respondToAfd\": \"NONE\",\r\n              \"colorMetadata\": \"INSERT\"\r\n            },\r\n            \"audioDescriptions\": [\r\n              {\r\n                \"audioTypeControl\": \"FOLLOW_INPUT\",\r\n                \"codecSettings\": {\r\n                  \"codec\": \"AAC\",\r\n                  \"aacSettings\": {\r\n                    \"audioDescriptionBroadcasterMix\": \"NORMAL\",\r\n                    \"bitrate\": 96000,\r\n                    \"rateControlMode\": \"CBR\",\r\n                    \"codecProfile\": \"LC\",\r\n                    \"codingMode\": \"CODING_MODE_2_0\",\r\n                    \"rawFormat\": \"NONE\",\r\n                    \"sampleRate\": 48000,\r\n                    \"specification\": \"MPEG4\"\r\n                  }\r\n                },\r\n                \"languageCodeControl\": \"FOLLOW_INPUT\"\r\n              }\r\n            ]\r\n          }\r\n        ],\r\n        \"outputGroupSettings\": {\r\n          \"type\": \"FILE_GROUP_SETTINGS\",\r\n          \"fileGroupSettings\": {\r\n            \"destination\": \"s3://test/test\"\r\n          }\r\n        }\r\n      }\r\n    ],\r\n    \"adAvailOffset\": 0,\r\n    \"inputs\": [\r\n      {\r\n        \"audioSelectors\": {\r\n          \"Audio Selector 1\": {\r\n            \"offset\": 0,\r\n            \"defaultSelection\": \"DEFAULT\",\r\n            \"programSelection\": 1\r\n          }\r\n        },\r\n        \"videoSelector\": {\r\n          \"colorSpace\": \"FOLLOW\"\r\n        },\r\n        \"filterEnable\": \"AUTO\",\r\n        \"psiControl\": \"USE_PSI\",\r\n        \"filterStrength\": 0,\r\n        \"deblockFilter\": \"DISABLED\",\r\n        \"denoiseFilter\": \"DISABLED\",\r\n        \"timecodeSource\": \"EMBEDDED\",\r\n        \"fileInput\": \"s3://bucket/file.mp4\"\r\n      }\r\n    ]\r\n  }\r\n}"
		},
		{
			"id": "37896178-5574-1b03-858f-8c3dd362c231",
			"headers": "Content-Type: application/json\nHost: <custom-account-id>.mediaconvert.<region>.amazonaws.com\nContent-Length: 5274\nX-Amz-Date: 20180702T200725Z\nAuthorization: AWS4-HMAC-SHA256 Credential=AccessKey/20180702/supported-region/mediaconvert/aws4_request, SignedHeaders=content-length;content-type;host;x-amz-date, Signature=345d7d88d77bb9b227f6044a64b1c9cc76f0556f0365256cb2931acfabcd413b\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				},
				{
					"key": "Host",
					"value": "<custom-account-id>.mediaconvert.<region>.amazonaws.com",
					"description": "",
					"enabled": true
				},
				{
					"key": "Content-Length",
					"value": "5274",
					"description": "",
					"enabled": true
				},
				{
					"key": "X-Amz-Date",
					"value": "20180702T200725Z",
					"description": "",
					"enabled": true
				},
				{
					"key": "Authorization",
					"value": "AWS4-HMAC-SHA256 Credential=AccessKey/20180702/supported-region/mediaconvert/aws4_request, SignedHeaders=content-length;content-type;host;x-amz-date, Signature=345d7d88d77bb9b227f6044a64b1c9cc76f0556f0365256cb2931acfabcd413b",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobTemplates",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530563456504,
			"name": "Create Job Template",
			"description": "",
			"collectionId": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
			"responses": [],
			"rawModeData": "{\n\t\"name\": \"Job Template Test\",\n\t\"description\": \"Job Template Test\",\n\t\"settings\":{\n    \"outputGroups\": [\n        {\n            \"name\": \"File Group\",\n            \"outputs\": [\n                {\n                    \"containerSettings\": {\n                        \"container\": \"MP4\",\n                        \"mp4Settings\": {\n                            \"cslgAtom\": \"INCLUDE\",\n                            \"freeSpaceBox\": \"EXCLUDE\",\n                            \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\n                        }\n                    },\n                    \"videoDescription\": {\n                        \"width\": 640,\n                        \"scalingBehavior\": \"DEFAULT\",\n                        \"height\": 480,\n                        \"videoPreprocessors\": {\n                            \"deinterlacer\": {\n                                \"algorithm\": \"INTERPOLATE\",\n                                \"mode\": \"DEINTERLACE\",\n                                \"control\": \"NORMAL\"\n                            }\n                        },\n                        \"timecodeInsertion\": \"DISABLED\",\n                        \"antiAlias\": \"ENABLED\",\n                        \"sharpness\": 50,\n                        \"codecSettings\": {\n                            \"codec\": \"H_264\",\n                            \"h264Settings\": {\n                                \"interlaceMode\": \"PROGRESSIVE\",\n                                \"parNumerator\": 1,\n                                \"numberReferenceFrames\": 3,\n                                \"syntax\": \"DEFAULT\",\n                                \"softness\": 0,\n                                \"framerateDenominator\": 1001,\n                                \"gopClosedCadence\": 1,\n                                \"hrdBufferInitialFillPercentage\": 90,\n                                \"gopSize\": 2,\n                                \"slices\": 1,\n                                \"gopBReference\": \"ENABLED\",\n                                \"hrdBufferSize\": 3000000,\n                                \"slowPal\": \"DISABLED\",\n                                \"parDenominator\": 1,\n                                \"spatialAdaptiveQuantization\": \"ENABLED\",\n                                \"temporalAdaptiveQuantization\": \"ENABLED\",\n                                \"flickerAdaptiveQuantization\": \"ENABLED\",\n                                \"entropyEncoding\": \"CABAC\",\n                                \"bitrate\": 1500000,\n                                \"framerateControl\": \"SPECIFIED\",\n                                \"rateControlMode\": \"CBR\",\n                                \"codecProfile\": \"MAIN\",\n                                \"telecine\": \"NONE\",\n                                \"framerateNumerator\": 24000,\n                                \"minIInterval\": 0,\n                                \"adaptiveQuantization\": \"HIGH\",\n                                \"codecLevel\": \"LEVEL_3\",\n                                \"fieldEncoding\": \"PAFF\",\n                                \"sceneChangeDetect\": \"ENABLED\",\n                                \"qualityTuningLevel\": \"MULTI_PASS_HQ\",\n                                \"framerateConversionAlgorithm\": \"DUPLICATE_DROP\",\n                                \"unregisteredSeiTimecode\": \"DISABLED\",\n                                \"gopSizeUnits\": \"SECONDS\",\n                                \"parControl\": \"SPECIFIED\",\n                                \"numberBFramesBetweenReferenceFrames\": 3,\n                                \"repeatPps\": \"DISABLED\"\n                            }\n                        },\n                        \"afdSignaling\": \"NONE\",\n                        \"dropFrameTimecode\": \"ENABLED\",\n                        \"respondToAfd\": \"NONE\",\n                        \"colorMetadata\": \"INSERT\"\n                    },\n                    \"audioDescriptions\": [\n                        {\n                            \"audioTypeControl\": \"FOLLOW_INPUT\",\n                            \"audioSourceName\": \"Audio Selector 1\",\n                            \"codecSettings\": {\n                                \"codec\": \"AAC\",\n                                \"aacSettings\": {\n                                    \"audioDescriptionBroadcasterMix\": \"NORMAL\",\n                                    \"bitrate\": 160000,\n                                    \"rateControlMode\": \"CBR\",\n                                    \"codecProfile\": \"LC\",\n                                    \"codingMode\": \"CODING_MODE_2_0\",\n                                    \"rawFormat\": \"NONE\",\n                                    \"sampleRate\": 48000,\n                                    \"specification\": \"MPEG4\"\n                                }\n                            },\n                            \"languageCodeControl\": \"FOLLOW_INPUT\",\n                            \"audioType\": 0\n                        }\n                    ],\n                    \"nameModifier\": \"_settings\"\n                },\n                {\n                    \"preset\": \"System-Generic_Hd_Mp4_Hevc_Aac_16x9_1920x1080p_50Hz_6Mbps\",\n                    \"nameModifier\": \"_preset\"\n                }\n            ],\n            \"outputGroupSettings\": {\n                \"type\": \"FILE_GROUP_SETTINGS\",\n                \"fileGroupSettings\": {}\n            }\n        }\n    ],\n    \"adAvailOffset\": 0\n\t}\n}\t"
		},
		{
			"id": "3a124a9e-e437-2a47-b8e1-eb51e121311c",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/presets",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530562249778,
			"name": "Create Job Preset",
			"description": "",
			"collectionId": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
			"responses": [],
			"rawModeData": "{\r\n\t\"name\": \"Test Preset\",\r\n\t\"description\": \"Test Preset\",\r\n\t\"settings\":{\r\n  \"videoDescription\": {\r\n    \"width\": 1280,\r\n    \"scalingBehavior\": \"DEFAULT\",\r\n    \"height\": 720,\r\n    \"videoPreprocessors\": {\r\n      \"deinterlacer\": {\r\n        \"algorithm\": \"INTERPOLATE\",\r\n        \"mode\": \"DEINTERLACE\",\r\n        \"control\": \"NORMAL\"\r\n      }\r\n    },\r\n    \"timecodeInsertion\": \"DISABLED\",\r\n    \"antiAlias\": \"ENABLED\",\r\n    \"sharpness\": 50,\r\n    \"codecSettings\": {\r\n      \"codec\": \"H_264\",\r\n      \"h264Settings\": {\r\n        \"interlaceMode\": \"PROGRESSIVE\",\r\n        \"parNumerator\": 1,\r\n        \"numberReferenceFrames\": 3,\r\n        \"syntax\": \"DEFAULT\",\r\n        \"softness\": 0,\r\n        \"framerateDenominator\": 1001,\r\n        \"gopClosedCadence\": 1,\r\n        \"hrdBufferInitialFillPercentage\": 90,\r\n        \"gopSize\": 2,\r\n        \"slices\": 1,\r\n        \"gopBReference\": \"ENABLED\",\r\n        \"hrdBufferSize\": 9000000,\r\n        \"slowPal\": \"DISABLED\",\r\n        \"parDenominator\": 1,\r\n        \"spatialAdaptiveQuantization\": \"ENABLED\",\r\n        \"temporalAdaptiveQuantization\": \"ENABLED\",\r\n        \"flickerAdaptiveQuantization\": \"ENABLED\",\r\n        \"entropyEncoding\": \"CABAC\",\r\n        \"bitrate\": 4500000,\r\n        \"framerateControl\": \"SPECIFIED\",\r\n        \"rateControlMode\": \"CBR\",\r\n        \"codecProfile\": \"HIGH\",\r\n        \"telecine\": \"NONE\",\r\n        \"framerateNumerator\": 24000,\r\n        \"minIInterval\": 0,\r\n        \"adaptiveQuantization\": \"HIGH\",\r\n        \"codecLevel\": \"LEVEL_4\",\r\n        \"fieldEncoding\": \"PAFF\",\r\n        \"sceneChangeDetect\": \"ENABLED\",\r\n        \"qualityTuningLevel\": \"MULTI_PASS_HQ\",\r\n        \"framerateConversionAlgorithm\": \"DUPLICATE_DROP\",\r\n        \"unregisteredSeiTimecode\": \"DISABLED\",\r\n        \"gopSizeUnits\": \"SECONDS\",\r\n        \"parControl\": \"SPECIFIED\",\r\n        \"numberBFramesBetweenReferenceFrames\": 3,\r\n        \"repeatPps\": \"DISABLED\"\r\n      }\r\n    },\r\n    \"afdSignaling\": \"NONE\",\r\n    \"dropFrameTimecode\": \"ENABLED\",\r\n    \"respondToAfd\": \"NONE\",\r\n    \"colorMetadata\": \"INSERT\"\r\n  },\r\n  \"audioDescriptions\": [\r\n    {\r\n      \"audioTypeControl\": \"FOLLOW_INPUT\",\r\n      \"audioSourceName\": \"Audio Selector 1\",\r\n      \"codecSettings\": {\r\n        \"codec\": \"AAC\",\r\n        \"aacSettings\": {\r\n          \"audioDescriptionBroadcasterMix\": \"NORMAL\",\r\n          \"bitrate\": 160000,\r\n          \"rateControlMode\": \"CBR\",\r\n          \"codecProfile\": \"LC\",\r\n          \"codingMode\": \"CODING_MODE_2_0\",\r\n          \"rawFormat\": \"NONE\",\r\n          \"sampleRate\": 48000,\r\n          \"specification\": \"MPEG4\"\r\n        }\r\n      },\r\n      \"languageCodeControl\": \"FOLLOW_INPUT\",\r\n      \"audioType\": 0\r\n    }\r\n  ],\r\n  \"containerSettings\": {\r\n    \"container\": \"MP4\",\r\n    \"mp4Settings\": {\r\n      \"cslgAtom\": \"INCLUDE\",\r\n      \"freeSpaceBox\": \"EXCLUDE\",\r\n      \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\r\n    }\r\n  }\r\n}\r\n}"
		},
		{
			"id": "b4a440ea-e235-fefa-636f-d0f5da8143f5",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobs",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530561464458,
			"name": "Submit MP4 Job (Using Preset)",
			"description": "",
			"collectionId": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
			"responses": [],
			"rawModeData": "{\r\n  \"userMetadata\": {},\r\n  \"role\": \"ROLE ARN HERE\",\r\n  \"settings\": {\r\n    \"outputGroups\": [\r\n      {\r\n        \"name\": \"File Group\",\r\n        \"outputs\": [\r\n          {\r\n            \"containerSettings\": {\r\n              \"container\": \"MP4\",\r\n              \"mp4Settings\": {\r\n                \"cslgAtom\": \"INCLUDE\",\r\n                \"freeSpaceBox\": \"EXCLUDE\",\r\n                \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\r\n              }\r\n            },\r\n            \"preset\": \"System-Generic_Sd_Mp4_Avc_Aac_4x3_640x480p_24Hz_1.5Mbps\"\r\n          }\r\n        ],\r\n        \"outputGroupSettings\": {\r\n          \"type\": \"FILE_GROUP_SETTINGS\",\r\n          \"fileGroupSettings\": {\r\n            \"destination\": \"s3://test/test\"\r\n          }\r\n        }\r\n      }\r\n    ],\r\n    \"adAvailOffset\": 0,\r\n    \"inputs\": [\r\n      {\r\n        \"audioSelectors\": {\r\n          \"Audio Selector 1\": {\r\n            \"offset\": 0,\r\n            \"defaultSelection\": \"DEFAULT\",\r\n            \"programSelection\": 1\r\n          }\r\n        },\r\n        \"videoSelector\": {\r\n          \"colorSpace\": \"FOLLOW\"\r\n        },\r\n        \"filterEnable\": \"AUTO\",\r\n        \"psiControl\": \"USE_PSI\",\r\n        \"filterStrength\": 0,\r\n        \"deblockFilter\": \"DISABLED\",\r\n        \"denoiseFilter\": \"DISABLED\",\r\n        \"timecodeSource\": \"EMBEDDED\",\r\n        \"fileInput\": \"s3://bucket/file.mp4\"\r\n      }\r\n    ]\r\n  }\r\n}"
		},
		{
			"id": "dbad1515-df7d-fbc7-84ad-bd97688ee0dd",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobs",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1530562495762,
			"name": "Submit Job (Using Template)",
			"description": "",
			"collectionId": "7f8f50a7-df20-f8c6-0180-9fe2eab4e285",
			"responses": [],
			"rawModeData": "{\r\n  \"userMetadata\": {},\r\n  \"role\": \"ROLE ARN HERE\",\r\n  \"jobTemplate\": \"Job Template Test\",\r\n  \"settings\": {\r\n    \"outputGroups\": [\r\n      {\r\n        \"outputGroupSettings\": {\r\n          \"fileGroupSettings\": {\r\n            \"destination\": \"s3://test/test\"\r\n          }\r\n        }\r\n      }\r\n    ],\r\n    \"adAvailOffset\": 0,\r\n    \"inputs\": [\r\n      {\r\n        \"audioSelectors\": {\r\n          \"Audio Selector 1\": {\r\n            \"offset\": 0,\r\n            \"defaultSelection\": \"DEFAULT\",\r\n            \"programSelection\": 1\r\n          }\r\n        },\r\n        \"videoSelector\": {\r\n          \"colorSpace\": \"FOLLOW\"\r\n        },\r\n        \"filterEnable\": \"AUTO\",\r\n        \"psiControl\": \"USE_PSI\",\r\n        \"filterStrength\": 0,\r\n        \"deblockFilter\": \"DISABLED\",\r\n        \"denoiseFilter\": \"DISABLED\",\r\n        \"timecodeSource\": \"EMBEDDED\",\r\n        \"fileInput\": \"s3://bucket/file.mp4\"\r\n      }\r\n    ]\r\n  }\r\n}"
		}
	]
}
```

## MediaConvert resource tagging collection<a name="tagging-collection"></a>

```
{
	"id": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
	"name": "AWS Elemental MediaConvert Resource Tagging ",
	"description": "How to use resource tagging ",
	"order": [
		"fe9449b1-990a-749e-6335-40f469162723",
		"59e4b5cd-7b62-b557-e8ed-ea369b3c08ea",
		"4f203fc8-4201-e60d-1d7d-c305d5714d82",
		"bc666e76-0251-ade4-97e3-21dd3bb89617",
		"c0e01125-0457-8a06-3cb6-f2902dd13fad",
		"8d91c8d3-fa3e-8835-e769-24224baf3334"
	],
	"folders": [],
	"folders_order": [],
	"timestamp": 1531246223825,
	"owner": "2332976",
	"public": false,
	"requests": [
		{
			"id": "4f203fc8-4201-e60d-1d7d-c305d5714d82",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/tags",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248443924,
			"name": "Tag Existing Preset",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\r\n        \"arn\": \"arn:aws:mediaconvert:eu-west-1:111122223333:presets/1080pMP4Preset\",\r\n        \"Tags\": {\r\n            \"CostCenter\": \"BU-Carrot\"\r\n        }\r\n}"
		},
		{
			"id": "59e4b5cd-7b62-b557-e8ed-ea369b3c08ea",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/tags",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248413882,
			"name": "Tag Existing Job Template",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\r\n        \"arn\": \"arn:aws:mediaconvert:region-name-1:111122223333:jobTemplates/MP4-ABR-Template\",\r\n        \"Tags\": {\r\n            \"CostCenter\": \"BU-Apple\"\r\n        }\r\n}"
		},
		{
			"id": "8d91c8d3-fa3e-8835-e769-24224baf3334",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/tags/arn%3Aaws%3Amediaconvert%3Aregion-name-1%3A111122223333%3Aqueues%2FQueueP2",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "GET",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248542197,
			"name": "Specific Resource ARN",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\r\n  \"userMetadata\": {},\r\n  \"role\": \"ROLE ARN HERE\",\r\n  \"settings\": {\r\n    \"outputGroups\": [\r\n      {\r\n        \"name\": \"File Group\",\r\n        \"outputs\": [\r\n          {\r\n            \"containerSettings\": {\r\n              \"container\": \"MP4\",\r\n              \"mp4Settings\": {\r\n                \"cslgAtom\": \"INCLUDE\",\r\n                \"freeSpaceBox\": \"EXCLUDE\",\r\n                \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\r\n              }\r\n            },\r\n            \"preset\": \"System-Generic_Sd_Mp4_Avc_Aac_4x3_640x480p_24Hz_1.5Mbps\"\r\n          }\r\n        ],\r\n        \"outputGroupSettings\": {\r\n          \"type\": \"FILE_GROUP_SETTINGS\",\r\n          \"fileGroupSettings\": {\r\n            \"destination\": \"s3://test/test\"\r\n          }\r\n        }\r\n      }\r\n    ],\r\n    \"adAvailOffset\": 0,\r\n    \"inputs\": [\r\n      {\r\n        \"audioSelectors\": {\r\n          \"Audio Selector 1\": {\r\n            \"offset\": 0,\r\n            \"defaultSelection\": \"DEFAULT\",\r\n            \"programSelection\": 1\r\n          }\r\n        },\r\n        \"videoSelector\": {\r\n          \"colorSpace\": \"FOLLOW\"\r\n        },\r\n        \"filterEnable\": \"AUTO\",\r\n        \"psiControl\": \"USE_PSI\",\r\n        \"filterStrength\": 0,\r\n        \"deblockFilter\": \"DISABLED\",\r\n        \"denoiseFilter\": \"DISABLED\",\r\n        \"timecodeSource\": \"EMBEDDED\",\r\n        \"fileInput\": \"s3://bucket/file.mp4\"\r\n      }\r\n    ]\r\n  }\r\n}"
		},
		{
			"id": "bc666e76-0251-ade4-97e3-21dd3bb89617",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/tags",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "DELETE",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248490219,
			"name": "Delete Tag from Resource",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\r\n\"arn\":\"arn:aws:mediaconvert:region-name-1:111122223333:queues/QueueP2\" ,\r\n \"TagKeys\": [\r\n        \"CostCenter\"\r\n        ]\r\n}"
		},
		{
			"id": "c0e01125-0457-8a06-3cb6-f2902dd13fad",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/jobTemplates",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248762262,
			"name": "Create New Resource (Job Template) with Tags",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\n\t\"name\": \"Job Template Test with Resource Tags\",\n\t\"description\": \"Job Template Test\",\n\t\"tags\":{\n\t\t\"CostCenter\": \"BU-Banana\"\n\t},\n\t\"settings\":{\n    \"outputGroups\": [\n        {\n            \"name\": \"File Group\",\n            \"outputs\": [\n                {\n                    \"containerSettings\": {\n                        \"container\": \"MP4\",\n                        \"mp4Settings\": {\n                            \"cslgAtom\": \"INCLUDE\",\n                            \"freeSpaceBox\": \"EXCLUDE\",\n                            \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\n                        }\n                    },\n                    \"videoDescription\": {\n                        \"width\": 640,\n                        \"scalingBehavior\": \"DEFAULT\",\n                        \"height\": 480,\n                        \"videoPreprocessors\": {\n                            \"deinterlacer\": {\n                                \"algorithm\": \"INTERPOLATE\",\n                                \"mode\": \"DEINTERLACE\",\n                                \"control\": \"NORMAL\"\n                            }\n                        },\n                        \"timecodeInsertion\": \"DISABLED\",\n                        \"antiAlias\": \"ENABLED\",\n                        \"sharpness\": 50,\n                        \"codecSettings\": {\n                            \"codec\": \"H_264\",\n                            \"h264Settings\": {\n                                \"interlaceMode\": \"PROGRESSIVE\",\n                                \"parNumerator\": 1,\n                                \"numberReferenceFrames\": 3,\n                                \"syntax\": \"DEFAULT\",\n                                \"softness\": 0,\n                                \"framerateDenominator\": 1001,\n                                \"gopClosedCadence\": 1,\n                                \"hrdBufferInitialFillPercentage\": 90,\n                                \"gopSize\": 2,\n                                \"slices\": 1,\n                                \"gopBReference\": \"ENABLED\",\n                                \"hrdBufferSize\": 3000000,\n                                \"slowPal\": \"DISABLED\",\n                                \"parDenominator\": 1,\n                                \"spatialAdaptiveQuantization\": \"ENABLED\",\n                                \"temporalAdaptiveQuantization\": \"ENABLED\",\n                                \"flickerAdaptiveQuantization\": \"ENABLED\",\n                                \"entropyEncoding\": \"CABAC\",\n                                \"bitrate\": 1500000,\n                                \"framerateControl\": \"SPECIFIED\",\n                                \"rateControlMode\": \"CBR\",\n                                \"codecProfile\": \"MAIN\",\n                                \"telecine\": \"NONE\",\n                                \"framerateNumerator\": 24000,\n                                \"minIInterval\": 0,\n                                \"adaptiveQuantization\": \"HIGH\",\n                                \"codecLevel\": \"LEVEL_3\",\n                                \"fieldEncoding\": \"PAFF\",\n                                \"sceneChangeDetect\": \"ENABLED\",\n                                \"qualityTuningLevel\": \"MULTI_PASS_HQ\",\n                                \"framerateConversionAlgorithm\": \"DUPLICATE_DROP\",\n                                \"unregisteredSeiTimecode\": \"DISABLED\",\n                                \"gopSizeUnits\": \"SECONDS\",\n                                \"parControl\": \"SPECIFIED\",\n                                \"numberBFramesBetweenReferenceFrames\": 3,\n                                \"repeatPps\": \"DISABLED\"\n                            }\n                        },\n                        \"afdSignaling\": \"NONE\",\n                        \"dropFrameTimecode\": \"ENABLED\",\n                        \"respondToAfd\": \"NONE\",\n                        \"colorMetadata\": \"INSERT\"\n                    },\n                    \"audioDescriptions\": [\n                        {\n                            \"audioTypeControl\": \"FOLLOW_INPUT\",\n                            \"audioSourceName\": \"Audio Selector 1\",\n                            \"codecSettings\": {\n                                \"codec\": \"AAC\",\n                                \"aacSettings\": {\n                                    \"audioDescriptionBroadcasterMix\": \"NORMAL\",\n                                    \"bitrate\": 160000,\n                                    \"rateControlMode\": \"CBR\",\n                                    \"codecProfile\": \"LC\",\n                                    \"codingMode\": \"CODING_MODE_2_0\",\n                                    \"rawFormat\": \"NONE\",\n                                    \"sampleRate\": 48000,\n                                    \"specification\": \"MPEG4\"\n                                }\n                            },\n                            \"languageCodeControl\": \"FOLLOW_INPUT\",\n                            \"audioType\": 0\n                        }\n                    ],\n                    \"nameModifier\": \"_settings\"\n                },\n                {\n                    \"preset\": \"System-Generic_Hd_Mp4_Hevc_Aac_16x9_1920x1080p_50Hz_6Mbps\",\n                    \"nameModifier\": \"_preset\"\n                }\n            ],\n            \"outputGroupSettings\": {\n                \"type\": \"FILE_GROUP_SETTINGS\",\n                \"fileGroupSettings\": {}\n            }\n        }\n    ],\n    \"adAvailOffset\": 0\n\t}\n}\t"
		},
		{
			"id": "fe9449b1-990a-749e-6335-40f469162723",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/tags",
			"queryParams": [
				{
					"key": "AWS_Region",
					"value": "eu-west-1",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Access_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				},
				{
					"key": "AWS_Secret_Key",
					"value": "KEY",
					"equals": false,
					"description": "",
					"enabled": false
				}
			],
			"preRequestScript": "",
			"pathVariables": {},
			"pathVariableData": [],
			"method": "POST",
			"data": [],
			"dataMode": "raw",
			"tests": "",
			"currentHelper": "awsSigV4",
			"helperAttributes": {
				"accessKey": "AccessKey",
				"secretKey": "SecretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1531248359729,
			"name": "Tag Existing Queue",
			"description": "",
			"collectionId": "7639779e-db69-b76f-cdbc-5ed1327fa0ca",
			"responses": [],
			"rawModeData": "{\r\n        \"arn\": \"arn:aws:mediaconvert:region-name-1:111122223333:queues/QueueP2\",\r\n        \"Tags\": {\r\n            \"CostCenter\": \"BU-Tomato\"\r\n        }\r\n}"
		}
	]
}
```