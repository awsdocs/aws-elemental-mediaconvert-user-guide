# Including SCTE\-35 Information in Your HLS Manifest<a name="including-scte-35-information-in-your-hls-manifest"></a>

For outputs in an HLS package, you can have the service include information in the HLS manifest about the SCTE\-35 markers that are in each of the outputs\.

**To include SCTE\-35 information in your HLS manifest \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, following the procedure in [Passing Through SCTE\-35 Markers from Your Input](passing-through-scte-35-markers.md) or [Specifying SCTE\-35 Markers Using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)\.

1. Enable ad markers in each of your **Apple HLS** output groups\.

   1. In the **Job** pane on the left, under **Output groups**, choose **Apple HLS**\.

   1. In the **Apple HLS group settings** section, choose **Advanced**\.

   1. Choose **Container settings**, then scroll down to find the **PID controls** section\.

   1. In the **Ad markers** section, choose one or both of **Elemental** and **SCTE\-35 enhanced**\. 

      For sample manifests created with each setting selected, see [Sample Manifest: Elemental Ad Markers](sample-manifest-elemental-ad-markers.md) and [Sample Manifest: SCTE\-35 Enhanced Ad Markers](sample-manifest-scte-35-enhanced-ad-markers.md)\.

1. If the source of your ad markers is an ESAM document, set these additional settings:

   1. Make sure that you entered XML for **Manifest confirm condition notification XML** during the procedure in [Specifying SCTE\-35 Markers Using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)\.

   1. For each output in each of your Apple HLS output groups, set **SCTE\-35 source** to **Passthrough**\.

      1. In the **Job** pane on the left, under **Output groups**, **Apple HLS**, choose an output\.

      1. In the **Output settings** section, choose **Transport stream settings**\.

      1. For **SCTE\-35 source**, choose **Passthrough**\.