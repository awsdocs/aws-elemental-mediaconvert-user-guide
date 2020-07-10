# Including SCTE\-35 markers in AWS Elemental MediaConvert outputs<a name="including-scte-35-markers"></a>

SCTE\-35 markers indicate where downstream systems can insert other content \(usually advertisements or local programs\)\. You can include SCTE\-35 markers in transport stream \(TS\), DASH, and HLS outputs\.

AWS Elemental MediaConvert puts SCTE\-35 markers into your outputs in one of two ways:
+ The service passes markers through from your input to the output\. For more information, see [Passing through SCTE\-35 markers from your input](passing-through-scte-35-markers.md)\.
+ The service inserts markers at the points that you specify in an Event Signaling and Management \(ESAM\) XML document\. For more information, see [Specifying SCTE\-35 markers using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)\.

Regardless of which way you put in the SCTE\-35 markers, for outputs that have them, you can optionally do the following:
+ You can have the service blank out audio and video during the ad avails indicated by the SCTE\-35 markers\. For more information, see [Enabling ad avail blanking](ad-avail-blanking.md)\.
+ For HLS outputs, you can have the service include SCTE\-35 information in your output HLS manifest\. For more information, see [Including SCTE\-35 information in your HLS manifest](including-scte-35-information-in-your-hls-manifest.md)\. MediaConvert doesn't write SCTE\-35 information to DASH manifests\.
**Note**  
MediaConvert does not process information from input manifests\.

By default, the service doesn't pass through SCTE\-35 markers from your input\. When you set up your job to pass through markers from the input or from an ESAM document, by default, the service doesn't include SCTE\-35 information in HLS manifests or do ad avail blanking\.

**Feature Limitations**  
Limitations to SCTE\-35 support are as follows:
+ You can either specify insertion points using ESAM XML or pass through SCTE\-35 messages from the input\. You can't do both\.
+ AWS Elemental MediaConvert supports only time\_signal messages, not splice\_insert messages\.
+ The service inserts SCTE\-35 messages only into the following outputs: 
  + Outputs in **File group** output groups with **MPEG\-2 Transport Stream** set for **Container**\. 

    Set the container for each output under **Output settings**, **Container**\.
  + Outputs in **DASH ISO** output groups\.
  + Outputs in **Apple HLS** output groups\.
+ The service forces IDR \(Instantaneous Decoder Refresh\) frames at the insertion points specified in your ESAM XML document only in outputs that are encoded with one of the following codecs: MPEG\-2, MPEG\-4 AVC \(H\.264\), or HEVC \(H\.265\)\. 

  Set the codec for each output under **Encoding settings**, **Video**, **Video codec**\.

**Topics**
+ [Passing through SCTE\-35 markers from your input](passing-through-scte-35-markers.md)
+ [Specifying SCTE\-35 markers using ESAM XML](specifying-scte-35-markers-using-esam-xml.md)
+ [Including SCTE\-35 information in your HLS manifest](including-scte-35-information-in-your-hls-manifest.md)
+ [Enabling ad avail blanking](ad-avail-blanking.md)