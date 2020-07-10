# Specifying SCTE\-35 markers using ESAM XML<a name="specifying-scte-35-markers-using-esam-xml"></a>

If your input video doesn't contain SCTE\-35 markers, but you need to specify ad insertion points in your outputs, you can provide Event Signaling and Management \(ESAM\) XML documents in your AWS Elemental MediaConvert job settings\. When you do, MediaConvert conditions your outputs  with IDR \(Instantaneous Decoder Refresh\) frames at the insertion points that you specify in the document\. In outputs that are also wrapped in MPEG2\-TS and HLS containers, MediaConvert inserts SCTE\-35 time\_signal messages at those points\. 

For your **Apple HLS** output groups, you also can optionally provide an HLS manifest conditioning XML document\. You can then set up your job to condition the manifests for your HLS outputs accordingly\.

**Note**  
To put SCTE\-35 markers in your MPEG2\-TS outputs, in addition to supplying the ESAM XML documents, you must also enable **ESAM SCTE\-35** on each output\. For more information, see the console procedure following this overview\.

**About Timecodes in Your ESAM Documents**  
Specify the insertion points in your XML documents relative to the timing of the final output, after input clipping and stitching\. Start your timing from 00:00:00:00, regardless of your timecode settings\. Use the following 24\-hour format with a frame number: HH:MM:SS:FF\.

For example, a job has the following three inputs: a five\-minute preroll, a one\-hour film, and a five\-minute postroll\. You use input clipping to clip just the final 20 minutes of your one\-hour input\. So your output with preroll and postroll is 30 minutes long\. If you want your first insertion point to appear three minutes into the main content, you would specify it at eight minutes—three minutes after your five\-minute preroll\. 

**To include ESAM XML documents in your job settings \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. In the **Job** pane on the left, in the **Job settings** section, choose **Settings**\.

1. In the **Ad signaling** section, enable **Event signaling and messaging \(ESAM\)**\.

1. For **Signal processing notification XML**, enter your ESAM signaling XML document as text\. For an example, see [Example ESAM XML signal processing notification](example-esam-xml.md)\.
**Note**  
By default, MediaConvert adds a four\-second preroll to the ESAM payload\. This might result in MediaConvert placing the SCTE\-35 message one segment earlier than the cue marker designates in the HLS manifest\. To remove the preroll, set `responseSignalPreroll` to zero\. This setting is a child of [EsamSettings](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs-id.html#jobs-id-model-esamsettings)\.

1. Optionally, if you want to include information about your SCTE\-35 markers in your HLS manifests, for **Manifest confirm condition notification XML**, enter your ESAM manifest conditional XML document as text\. MediaConvert doesn't include information about your SCTE\-35 markers in your DASH manifests\.

   To insert SCTE\-35 markers in the transport stream as well as in the manifest, set the `dataPassThrough` attribute in your MCC document to `"true"`\. If you don't want markers in the transport stream, remove the `dataPassThrough` attributes\.

   For an example, see [Example ESAM XML Manifest Confirm Condition Notification](example-esam-xml-manifest-conditioning.md)\. 

1. For each MPEG2\-TS output where you want SCTE\-35 markers, enable the markers:

   1. In the **Job** pane on the left, under **Output groups**, **File group**, choose the output\.

   1. Confirm that it is an MPEG2\-TS output\. In the **Output settings** section, make sure that **Container** is set to **MPEG\-2 Transport Stream**\.

   1. Choose **Container settings**, and then scroll down to find the **PID controls** section\.

   1. For **ESAM SCTE\-35** choose **Enabled**\.

   1. For **SCTE\-35 source**, keep the default **None**\.

1. Do this step only for any **Apple HLS** output groups in your job\.

   If you want to condition your HLS manifest with your ESAM insertion points, follow the procedure in [Including SCTE\-35 information in your HLS manifest](including-scte-35-information-in-your-hls-manifest.md)\. Otherwise, follow these steps to confirm that the following settings are still in their default state:

   1. Make sure that **Manifest confirm condition notification XML**, discussed in a previous step of this procedure, is empty\.

   1. For each **Apple HLS** output group in your job, confirm that you have kept **Ad Markers** unchecked\.

      1. In the **Job** pane on the left, under **Output groups**, choose **Apple HLS**\.

      1. In the **Apple HLS group settings** section, choose **Advanced**\.

      1. In the **Ad markers** section, clear the **Elemental** and **SCTE\-35 enhanced** check boxes\.

   1. For each output in your **Apple HLS** output groups, confirm that **SCTE\-35 source** is set to **None**:

      1. In the **Job** pane on the left, under **Output groups**, **Apple HLS**, choose an output\.

      1. In the **Output settings** section, choose **Transport stream settings**\.

      1. For **SCTE\-35 source**, choose **None**\.

**To include ESAM XML documents in your jobs settings \(API, SDK, AWS CLI\)**

1. Include the [`esam` property](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-jobsettings-esam) and its children at the root of the job settings in your JSON job specification\. These properties are shown in the following example\.

   1.  Include your ESAM signal processing XML specification as a string in the setting `sccXml`\. 

   1. Optionally, include a manifest confirm condition XML notification document as a string in the setting `mccXml`:

   ```
     "esam": {
       "responseSignalPreroll": 4000,
       "signalProcessingNotification": {
         "sccXml": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<SignalProcessingNotification ..."
       },
       "manifestConfirmConditionNotification": {
         "mccXml": "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"yes\"?>\n<ns2:ManifestConfirmConditionNotification ... " 
       }
   ```

1. For each M2TS \(MPEG2 Transport Stream\) output in your job, set your JSON job specification as shown in the following example\. Include the property [https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m2tssettings-scte35esam](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m2tssettings-scte35esam)\. Set [https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m2tssettings-scte35source](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m2tssettings-scte35source) to `NONE`\.

   ```
     "outputs": [
           {
             "extension": "m2ts",
             "containerSettings": {
               "container": "M2TS",
               "m2tsSettings": {
                 ...
   
                 "scte35Esam": {
                   "scte35EsamPid": 508
                 },
                 ...
                 "scte35Source": "NONE"
               }
   ```

1. If you want to condition your HLS manifests with SCTE\-35 information, for each Apple HLS output group in your job, include the following\. These settings are shown in the example at the end of this step:
   +  Set [https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m3u8settings-scte35source](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-m3u8settings-scte35source) to `PASSTHROUGH`\.
   + Include [https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-hlsgroupsettings-admarkers](https://docs.aws.amazon.com/mediaconvert/latest/apireference/jobs.html#jobs-prop-hlsgroupsettings-admarkers) and list one or both of `ELEMENTAL_SCTE35` or `ELEMENTAL` in an array\.

     For sample manifests created with each setting selected, see [Sample manifest: Elemental ad markers](sample-manifest-elemental-ad-markers.md) and [Sample manifest: SCTE\-35 enhanced ad markers](sample-manifest-scte-35-enhanced-ad-markers.md)\.

   If you don't want to condition your HLS manifests with SCTE\-35 information, keep the default setting `NONE` for `scte35Source` and don't include `adMarkers`:

   ```
     "outputGroups": [
       {
         "customName": "apple_hls",
         "outputGroupSettings": {
           "type": "HLS_GROUP_SETTINGS",
           "hlsGroupSettings": {
             "adMarkers": [
               "ELEMENTAL_SCTE35"
             ],
             ...
   
           }
         },
         "outputs": [
           {
             "extension": "m3u8",
             "nameModifier": "high",
             "outputSettings": {
               "hlsSettings": {
                 ...
               }
             },
             "containerSettings": {
               "container": "M3U8",
               "m3u8Settings": {
                 ...
                 "scte35Source": "PASSTHROUGH"
               }
   ```

1. Submit your job as usual\. 

   For information about submitting AWS Elemental MediaConvert jobs programmatically, see [Getting started with AWS Elemental MediaConvert using the AWS SDKs or the AWS CLI](https://docs.aws.amazon.com/mediaconvert/latest/apireference/custom-endpoints.html) and [Getting started with AWS Elemental MediaConvert using the API](https://docs.aws.amazon.com/mediaconvert/latest/apireference/getting-started.html)\.