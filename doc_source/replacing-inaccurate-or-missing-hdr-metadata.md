# Replacing inaccurate or missing HDR metadata<a name="replacing-inaccurate-or-missing-hdr-metadata"></a>

If your input video is missing HDR metadata, or has HDR metadata that is wrong, you can add it or overwrite it in the input video settings\. For HLG and HDR 10, you can specify the correct color space\. For HDR 10, you can also specify accurate master display information\.

**Note**  
You use the input settings to supply metadata that is wrong or missing from your input files\. Use output settings to do color space conversion\.

**To replace inaccurate or missing HDR metadata**

1. Set up your transcoding job as usual\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, choose your input\.

1. In the **Video selector** section on the right, for **Color space**, choose the accurate color space for your input video\.

1. For **Color space usage**, choose how AWS Elemental MediaConvert handles precedence between the input metadata and the value that you specify for **Color space**: 
   + Choose **Force** if you want MediaConvert to use the color space that you specify for **Color space** regardless of whether it is specified in the input video metadata\.
   + Choose **Fallback** if you want MediaConvert to use the color space that you specify for **Color space** only when the color space isn't present in the input video metadata\.

     This option is useful when you reuse job settings with different input files, for example, when you use output presets or when you duplicate a job\.

1. If your input is HDR 10, specify values for **HDR master display information** settings\. MediaConvert displays these settings when you set **Color space** to **HDR 10**\.

   These settings represent HDR 10 static metadata as specified in the standard SMPTE ST 2086 Mastering Display Color Volume\. MediaConvert includes the values that you specify here in the metadata of your HDR 10 outputs\.
**Note**  
Get your values for **HDR master display information** from a color grader\. Appropriate values for these settings depend on the video content and are different for each input\.