# Setting Up a Job for HDR<a name="hdr"></a>

MediaConvert ingests and outputs video in the following HDR formats:
+ HDR10 \(rec\. 2020 color space\)
+ HLG \(rec\. 2020 color space\)

and the following standard formats:
+ SDR \(rec\. 609 color space\)
+ SDR \(rec\. 709 color space\)

MediaConvert supports HDR with HEVC video assets in transport stream and DASH outputs\. 

You can create HDR output in the following ways:
+ Ingesting HDR content and outputting video in the same format\. 
+ Ingesting HDR content in one format and converting it to the other HDR format\. This process changes the video itself and automatically converts the metadata to match the content conversion\. 
+ Ingesting SDR content and converting the color space to an HDR format\. This process creates output that is formatted as HDR and automatically converts the metadata to match\.
**Note**  
This process doesn't upgrade the dynamic range of the video content itself\. Therefore, the output is formatted as HDR but looks the same as it would if you created it as an SDR output\.

You can't convert HDR video to SDR with MediaConvert\.

With HDR10 outputs, you handle color space metadata by passing through from the input, adding missing data, or correcting inaccurate data\.

MediaConvert automatically reads HDR metadata from the video source\. 

## Color Space Metadata Settings<a name="color-space-metadata-settings"></a>

By default, MediaConvert sets your color space to **Follow**, which means that your output color space is the same as your input color space, even if the color space changes over the course of the video\. 

Use the following checklist to modify the color space settings for your job\.


| Color correction task | How to do it | 
| --- | --- | 
| Replace any missing or inaccurate color space metadata in the input\.  |  [Correcting Input Color Space Metadata](correcting-input-color-space-metadata.md)  | 
| Configure each output stream to include or exclude color metadata as needed\.  |  [Inserting Color Metadata in the Output](inserting-color-metadata-in-the-output.md)  | 
| Apply color correction as needed in each output stream's preprocessors color correction selections\.  | [Correcting Color in the Output](correcting-color-in-the-output.md)  | 