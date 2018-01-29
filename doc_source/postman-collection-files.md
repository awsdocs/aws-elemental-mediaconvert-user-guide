# Postman Collection Files<a name="postman-collection-files"></a>

Import these collection files into Postman to access AWS Elemental MediaConvert via the REST API\.


+ [GET Collection](#postman-collection-GET)
+ [POST Collection](#postman-collection-POST)

## GET Collection<a name="postman-collection-GET"></a>

```
{
	"owner": "2332976",
	"lastUpdatedBy": "2332976",
	"lastRevision": 1921667904,
	"team": null,
	"id": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
	"name": "EMF Get",
	"description": "EMF Get Template",
	"folders_order": [],
	"order": [
		"bc671df5-4a85-54b6-f137-19cb70516fd2",
		"85318a0b-c490-3718-62eb-2a737de83af0",
		"1fd40def-ca4b-1842-c99a-778f62269010"
	],
	"folders": [],
	"hasRequests": true,
	"requests": [
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
				"secretKey": "ScretKey",
				"region": "supported-region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1513791262493,
			"name": "GET List Queue ",
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
			"time": 1507243078514,
			"name": "GET Queue Details",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
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
				"region": "supportedregion",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1510272337434,
			"name": "GET JOB ID",
			"description": "",
			"collectionId": "87fac2df-dd0f-b54a-b1f9-5b138cb4147f",
			"responses": []
		}
	]
}
```

## POST Collection<a name="postman-collection-POST"></a>

```
{
	"id": "a1be92f5-37d5-aaf0-06bb-14090d825c62",
	"name": "AWS Elemental MediaConvert POST",
	"description": "POST Template",
	"order": [
		"0fd3c4a5-fa08-2dbc-1f0a-955942664858",
		"d6ffaf05-0caa-35ee-8a3d-4457a96f4926"
	],
	"folders": [],
	"folders_order": [],
	"timestamp": 0,
	"owner": "2332976",
	"public": false,
	"requests": [
		{
			"id": "0fd3c4a5-fa08-2dbc-1f0a-955942664858",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://<custom-account-id>.mediaconvert.<region>.amazonaws.com/2017-08-29/",
			"folder": null,
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
			"time": 1510272274641,
			"name": "Post MP4 Job",
			"description": "",
			"collectionId": "a1be92f5-37d5-aaf0-06bb-14090d825c62",
			"responses": [],
			"rawModeData": "{\r\n  \"userMetadata\": {},\r\n  \"role\": \"ROLE ARN HERE\",\r\n  \"settings\": {\r\n    \"outputGroups\": [\r\n      {\r\n        \"name\": \"File Group\",\r\n        \"outputs\": [\r\n          {\r\n            \"containerSettings\": {\r\n              \"container\": \"MP4\",\r\n              \"mp4Settings\": {\r\n                \"cslgAtom\": \"INCLUDE\",\r\n                \"freeSpaceBox\": \"EXCLUDE\",\r\n                \"moovPlacement\": \"PROGRESSIVE_DOWNLOAD\"\r\n              }\r\n            },\r\n            \"videoDescription\": {\r\n              \"scalingBehavior\": \"DEFAULT\",\r\n              \"timecodeInsertion\": \"DISABLED\",\r\n              \"antiAlias\": \"ENABLED\",\r\n              \"sharpness\": 50,\r\n              \"codecSettings\": {\r\n                \"codec\": \"H_264\",\r\n                \"h264Settings\": {\r\n                  \"interlaceMode\": \"PROGRESSIVE\",\r\n                  \"numberReferenceFrames\": 1,\r\n                  \"syntax\": \"DEFAULT\",\r\n                  \"softness\": 0,\r\n                  \"gopClosedCadence\": 1,\r\n                  \"gopSize\": 90,\r\n                  \"slices\": 1,\r\n                  \"gopBReference\": \"DISABLED\",\r\n                  \"slowPal\": \"DISABLED\",\r\n                  \"spatialAdaptiveQuantization\": \"ENABLED\",\r\n                  \"temporalAdaptiveQuantization\": \"ENABLED\",\r\n                  \"flickerAdaptiveQuantization\": \"ENABLED\",\r\n                  \"entropyEncoding\": \"CABAC\",\r\n                  \"bitrate\": 5000000,\r\n                  \"framerateControl\": \"INITIALIZE_FROM_SOURCE\",\r\n                  \"rateControlMode\": \"CBR\",\r\n                  \"codecProfile\": \"MAIN\",\r\n                  \"telecine\": \"NONE\",\r\n                  \"minIInterval\": 0,\r\n                  \"adaptiveQuantization\": \"MEDIUM\",\r\n                  \"codecLevel\": \"AUTO\",\r\n                  \"fieldEncoding\": \"PAFF\",\r\n                  \"sceneChangeDetect\": \"ENABLED\",\r\n                  \"qualityTuningLevel\": \"SINGLE_PASS\",\r\n                  \"framerateConversionAlgorithm\": \"DUPLICATE_DROP\",\r\n                  \"unregisteredSeiTimecode\": \"DISABLED\",\r\n                  \"gopSizeUnits\": \"FRAMES\",\r\n                  \"parControl\": \"INITIALIZE_FROM_SOURCE\",\r\n                  \"numberBFramesBetweenReferenceFrames\": 2,\r\n                  \"repeatPps\": \"DISABLED\"\r\n                }\r\n              },\r\n              \"afdSignaling\": \"NONE\",\r\n              \"dropFrameTimecode\": \"ENABLED\",\r\n              \"respondToAfd\": \"NONE\",\r\n              \"colorMetadata\": \"INSERT\"\r\n            },\r\n            \"audioDescriptions\": [\r\n              {\r\n                \"audioTypeControl\": \"FOLLOW_INPUT\",\r\n                \"codecSettings\": {\r\n                  \"codec\": \"AAC\",\r\n                  \"aacSettings\": {\r\n                    \"audioDescriptionBroadcasterMix\": \"NORMAL\",\r\n                    \"bitrate\": 96000,\r\n                    \"rateControlMode\": \"CBR\",\r\n                    \"codecProfile\": \"LC\",\r\n                    \"codingMode\": \"CODING_MODE_2_0\",\r\n                    \"rawFormat\": \"NONE\",\r\n                    \"sampleRate\": 48000,\r\n                    \"specification\": \"MPEG4\"\r\n                  }\r\n                },\r\n                \"languageCodeControl\": \"FOLLOW_INPUT\"\r\n              }\r\n            ]\r\n          }\r\n        ],\r\n        \"outputGroupSettings\": {\r\n          \"type\": \"FILE_GROUP_SETTINGS\",\r\n          \"fileGroupSettings\": {\r\n            \"destination\": \"s3://test/test\"\r\n          }\r\n        }\r\n      }\r\n    ],\r\n    \"adAvailOffset\": 0,\r\n    \"inputs\": [\r\n      {\r\n        \"audioSelectors\": {\r\n          \"Audio Selector 1\": {\r\n            \"offset\": 0,\r\n            \"defaultSelection\": \"DEFAULT\",\r\n            \"programSelection\": 1\r\n          }\r\n        },\r\n        \"videoSelector\": {\r\n          \"colorSpace\": \"FOLLOW\"\r\n        },\r\n        \"filterEnable\": \"AUTO\",\r\n        \"psiControl\": \"USE_PSI\",\r\n        \"filterStrength\": 0,\r\n        \"deblockFilter\": \"DISABLED\",\r\n        \"denoiseFilter\": \"DISABLED\",\r\n        \"timecodeSource\": \"EMBEDDED\",\r\n        \"fileInput\": \"s3://bucket/file.mp4\"\r\n      }\r\n    ]\r\n  }\r\n}"
		},
		{
			"id": "d6ffaf05-0caa-35ee-8a3d-4457a96f4926",
			"headers": "Content-Type: application/json\n",
			"headerData": [
				{
					"key": "Content-Type",
					"value": "application/json",
					"description": "",
					"enabled": true
				}
			],
			"url": "https://mediaconvert.<region>.amazonaws.com/2017-08-29/endpoints",
			"folder": null,
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
				"region": "Supported Region",
				"service": "mediaconvert",
				"saveToRequest": true
			},
			"time": 1510272153358,
			"name": "POST Request Account Endpoint",
			"description": "",
			"collectionId": "a1be92f5-37d5-aaf0-06bb-14090d825c62",
			"responses": [],
			"rawModeData": ""
		}
	]
}
```