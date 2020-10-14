# Setting up an MXF output<a name="setting-up-an-mxf-job"></a>

To set up a job with an MXF output, you create the output in the **File group** output group and specify MXF as the output's container\.

**To set up your transcoding job with an MXF output \(console\)**

1.  Set up your job inputs and outputs as described in [Setting up a job](setting-up-a-job.md)\. Put your MXF output in the **File group** output group\.

1. On the **Create job** page, in the **Job** pane on the left, choose your output\.

1. In the **Output settings** section, for **Container**, choose **MXF container**\.

1. Optionally, specify values for the settings under **MXF container settings**:
   + **MXF profile**: To manually specify your MXF profile, choose it from the list\. If you keep the default value, **Auto**, MediaConvert chooses your MXF profile based on your video codec and resolution\. For more information, see [Default automatic selection of MXF profiles](default-automatic-selection-of-mxf-profiles.md)\.
   + **Copy AFD to MXF**: Ignore this setting unless you have AFD signaling set up in your output video stream\. If you do, and you want that information in both your video stream and the MXF wrapper, choose **Copy from video stream**\. If you want your AFD signaling only in your video stream, keep the default value **Don't copy**\.

1. In the **Encoding settings** section, choose a video codec\. 

   Your available choices in this list depend on what you choose for **MXF profile** in the previous step of this procedure:
   + When you keep the default value, **Auto**, for **MXF profile** then you can choose any video codec that is compatible with your output container\.
   + When you choose a specific profile for **MXF profile**, then your choices for **Video codec** include only the codecs that are valid with that profile\.

1. Optionally, specify your output video resolution for **Resolution \(w x h\)**\. This is the other setting that MediaConvert uses when automatically determining your MXF profile\.

   When you don't specify values for **Resolution \(w x h\)**, your output resolution is the same as your input resolution\.

1. Specify your other encoding settings as usual\. For information about each setting, choose the **Info** link next to the setting label\. 

**To set up your transcoding job with an MXF output \(API, CLI, or SDK\)**

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)
+ Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

  1. Follow the previous procedure for the console\.

  1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:

**Output settings**
+ **Container** \(`[container](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-containersettings-container)`\)
+ **MXF profile** \(`mxfSettings, [profile](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mxfsettings-profile)`\)

  For automatic profile selection, omit this setting from your JSON job specification\.
+ **Copy AFD to MXF** \(`mxfSettings, [afdSignaling](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-mxfsettings-afdsignaling)`\)

**Encoding settings**
+ **Video codec** \(`[codec](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videocodecsettings-codec)`\)

  This setting is a child of `outputs, videoDescription, codecSettings`\.
+ **Resolution, w** \(`[width](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videodescription-width)`\)

  This setting is a child of `outputs, videoDescription`\.
+ **Resolution, h** \(`[height](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-videodescription-height)`\)

  This setting is a child of `outputs, videoDescription`\.

In the MediaConvert console, **Auto** is the default value for **MXF profile**\. When you set up your job by directly editing your JSON job specification, for automatic profile selection, don't include `profile` under `MxfSettings`\.