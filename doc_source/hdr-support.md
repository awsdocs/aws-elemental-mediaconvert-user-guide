# HDR support in AWS Elemental MediaConvert<a name="hdr-support"></a>

AWS Elemental MediaConvert supports HDR with HEVC video assets in the following outputs: MPEG2\-TS, DASH, and CMAF\.

You can set up your CMAF outputs to be compatible with Apple HLS player devices\. For more information, see [Creating HDR HLS outputs that comply with the Apple specification](#creating-hdr-hls-outputs-that-comply-with-the-apple-specification)\.

## Supported formats and color spaces<a name="supported-formats-and-color-spaces"></a>

MediaConvert ingests and outputs video in the following HDR formats:
+ HDR10 \(rec\. 2020 color space\)
+ HLG \(rec\. 2020 color space\)

MediaConvert ingests and outputs video in the following standard formats:
+ SDR \(rec\. 601 color space\)
+ SDR \(rec\. 709 color space\)

## Supported color space conversions<a name="supported-color-space-conversions"></a>

Your input color space is set by your input video or by the values that you set for **Color space** and **Color space usage** in your input settings\. For more information about the input color space settings, see [Replacing inaccurate or missing HDR metadata](replacing-inaccurate-or-missing-hdr-metadata.md)\.

For information about how to convert the color space, see [Converting the color space](converting-the-color-space.md)\.

MediaConvert supports the following color space conversions:
+ From any supported HDR format to any other supported HDR format
+ From any supported SDR color space to any other supported SDR color space
+ From any supported SDR color space to any supported HDR format
**Note**  
Converting from SDR to HDR doesn't upgrade the dynamic range of the video content itself\. Therefore, the output is formatted as HDR but looks the same as it would if you created it as an SDR output\.
+ From any supported HDR format to any supported SDR color space
**Note**  
When professional color graders convert an asset from HDR to SDR, they make artistic decisions about where to map colors from the larger space that don't exist in the smaller space\. There is no standard formula to map these values automatically\. The tone mapping technology that MediaConvert uses to do automatic conversion from HDR to SDR approximates the outcome of manually regrading from HDR to SDR\. This automatic conversion works well with most content, but we recommend that you review your outputs to confirm the tone mapping results\.

## Creating HDR HLS outputs that comply with the Apple specification<a name="creating-hdr-hls-outputs-that-comply-with-the-apple-specification"></a>

For information about which Apple devices play back HDR content, see [Find and watch movies with 4K, HDR, Dolby Vision, or Dolby Atmos](https://support.apple.com/en-us/HT207949) in the Apple support documentation\.

To create HDR outputs that comply with the Apple specification, you must make specific choices for your encoding settings\. In the **Encoding settings** section for your output, specify these video settings as follows:
+ **Video codec** – Choose **HEVC \(H\.265\)**\.
+ **MP4 packaging type** – **HVC1**\.
+ **Profile** – Choose **Main10/High**\.
+ **Level** – Choose **5**\.

**Tip**  
The simplest way to find specific encoding settings in the console is to use your web browser’s search on page function\. For many browsers, this search is case sensitive\.