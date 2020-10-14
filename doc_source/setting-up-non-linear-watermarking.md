# Setting up your MediaConvert job for non\-linear watermarking<a name="setting-up-non-linear-watermarking"></a>

To use this feature, you must first establish a partnership with Nielsen and set up a Nielsen SID/TIC server in the AWS Cloud\. Contact Nielsen to download their SID/TIC server software, generate a WRR licence file, and receive installation and setup instructions\. For an overview of how the infrastructure works, see [How AWS Elemental MediaConvert interacts with your Nielsen SID/TIC server in the AWS Cloud](how-mediaconvert-interacts-with-your-nielsen-sid-tic-server-in-the-aws-cloud.md)\.

**To set up Nielsen non\-linear watermarking \(console\)**

1. Set up a Nielsen SID/TIC server system in the AWS Cloud\. For more information, contact Nielsen\.

1. Set up an Amazon S3 bucket to hold your Nielsen metadata \.zip file\. MediaConvert writes the metadata to this bucket\.

1.  Set up your job inputs and outputs as described in [Setting up a job](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings** choose **Settings**\.

1. In the **Partner integrations** section on the right, choose **Nielsen non\-linear watermarking**\.

1. Provide values for the settings that become visible when you enable **Nielsen non\-linear watermarking**\. For instructions and guidance about each of these settings, choose the **Info** link next to the setting label\.

1. Choose **Create**, at the bottom of the page, to run your job\.

1. Transfer the data in your metadata Amazon S3 bucket to Nielsen, according to their instructions\.

**To set up Nielsen non\-linear watermarking \(API, CLI, and SDK\)**

If you use the API, CLI, or an SDK, specify the relevant settings in your JSON job specification and then submit it programmatically with your job\. For more information about submitting your job programmatically, see one of the introductory topics of the *AWS Elemental MediaConvert API Reference*:
+ [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html)
+ [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)
+ Use the MediaConvert console to generate your JSON job specification\. We recommend this approach, because the console functions as an interactive validator against the MediaConvert job schema\. Follow these steps to generate your JSON job specification using the console:

  1. Follow the previous procedure for the console\.

  1. In the **Job** pane on the left, under **Job settings**, choose **Show job JSON**\.

Find additional information, including where each setting belongs in the job settings structure, in the *AWS Elemental MediaConvert API Reference*\. Links in this list go to information about the setting in that document:
+ **Nielsen non\-linear watermarking** \(`[nielsenNonLinearWatermark](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-jobsettings-nielsennonlinearwatermark)`\)
+ **Source watermark status** \(`[sourceWatermarkStatus](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-sourcewatermarkstatus)`\)
+ **Watermark types** \(`[activeWatermarkProcess](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-activewatermarkprocess)`\)
+ **SID** \(`[sourceId](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-sourceid)`\)
+ **CSID** \(`[cbetSourceId](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-cbetsourceid)`\)
+ **Asset ID** \(`[assetId](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-assetid)`\)
+ **Asset name** \(`[assetName](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-assetname)`\)
+ **Episode ID** \(`[episodeId](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-episodeid)`\)
+ **TIC server REST endpoint** \(`[ticServerUrl](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-ticserverurl)`\)
+ **ADI file** \(`[adiFilename](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-adifilename)`\)
+ **Metadata destination** \(`[metadataDestination](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-metadatadestination)`\)
+ **Share TICs across tracks** \(`[uniqueTicPerAudioTrack](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-nielsennonlinearwatermarksettings-uniqueticperaudiotrack)`\)