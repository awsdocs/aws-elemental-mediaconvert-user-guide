# Setting up your MediaConvert job for PCM to ID3 metadata<a name="setting-up-pcm-to-id3-metadata"></a>

To use this feature, your input must have PCM audio that contains Nielsen watermarks\. You provide your Nielsen distributor ID to MediaConvert and then, during the transcode, MediaConvert inserts the watermark information into the ID3 metadata of your output\.

**Feature restriction**  
You can put Nielsen watermarking information into the ID3 metadata of outputs in the following output groups only:
+ Apple HLS
+ File group, when your output container is MPEG\-2 Transport Stream

**To enable PCM to ID3 metadata \(console\)**

1.  Set up your job inputs and outputs as described in [Setting up a job](setting-up-a-job.md)\.

1. Enable PCM to ID3 metadata in the job\-wide settings\.

   1. On the **Create job** page, in the **Job** pane on the left, under **Job settings** choose **Settings**\.

   1. In the **Partner integrations** section on the right, choose **Nielsen PCM to ID3 metadata**\.

   1. For **Distributor ID**, provide the ID that Nielsen assigned to your organization\.

1. Enable PCM to ID3 metadata in the outputs where you want it\. Do these steps for each **Apple HLS** output that you want to have ID3 metadata\.

   1. In the **Job** pane on the left, choose the output\.

   1. In the **Output settings** section on the right, expand the section **Transport stream settings**\.

   1. For **Nielsen ID3**, choose **Insert**\.

1. Do these steps for each **File group** output that you want to have ID3 metadata\.

   1. In the **Job** pane on the left, choose the output\.

   1. In the **Output settings** section on the right, expand the section **Container settings**\.

   1. Scroll to the section **PID controls**\.

   1. For **Nielsen ID3**, choose **Insert**\.

**To enable PCM to ID3 metadata \(API, CLI, and SDK\)**

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)
+ Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

  1. Follow the previous procedure for the console\.

  1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:
+ **Nielsen PCM to ID3 metadata** \(`[nielsenConfiguration](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-jobsettings-nielsenconfiguration)`\)
+ **Distributor ID** \(`[distributorId](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsenconfiguration-distributorId)`\)
+ **Nielsen ID3**, for outputs in an **Apple HLS** output group \(`[nielsenId3](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m3u8settings-nielsenid3)`, child of `[m3u8Settings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-containersettings-m3u8settings)`\)
+ **Nielsen ID3**, for outputs in a **File group** output group \(`[nielsenId3](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m2tssettings-nielsenid3)`, child of `[m2tsSettings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-containersettings-m2tssettings)`\)