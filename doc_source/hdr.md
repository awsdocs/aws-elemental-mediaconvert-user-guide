# Setting up a job for HDR in AWS Elemental MediaConvert<a name="hdr"></a>

You can create HDR content with AWS Elemental MediaConvert in the following ways:

**Passing Through HDR Content**  
You can pass through HDR content by using an HDR input and creating outputs in the same format, with the same metadata\. To do that, you keep the color space default settings, choose HEVC for your codec, and choose a 10\-bit profile\. MediaConvert automatically reads the HDR metadata, including color space, from the video source\. For detailed instructions, see [Passing through HDR content](passing-through-hdr-content.md)\.

**Correcting Inaccurate or Missing HDR Metadata**  
To provide HDR 10 metadata that is not present in your input, or to correct metadata that is wrong, add it or overwrite it in the input video settings\. This doesn't change the video content and is different from the color space conversion that you can do in your output video settings\. For detailed instructions, see [Replacing inaccurate or missing HDR metadata](replacing-inaccurate-or-missing-hdr-metadata.md)\.

**Converting from an HDR Format to a Different HDR Format**  
You can convert your input color space to a different output color space\. You do that by choosing the output color space in the output **Color corrector** settings\. For detailed instructions, see [Converting the color space](converting-the-color-space.md)\.

**Changing SDR Input to HDR Format**  
If your input is SDR, you can convert the color space to an HDR format\. This process creates output that is formatted as HDR and automatically converts the metadata to match\. You do that by choosing the output color space in the output **Color corrector** settings\. For detailed instructions, see [Converting the color space](converting-the-color-space.md)\.

**Note**  
This process doesn't upgrade the dynamic range of the video content\. These outputs will play on HDR player devices, and they will appear generally brighter than the original SDR content\. But the results are not the same as content that has been remastered from SDR to HDR by a color grader\.

**Topics**
+ [HDR support in AWS Elemental MediaConvert](hdr-support.md)
+ [Passing through HDR content](passing-through-hdr-content.md)
+ [Replacing inaccurate or missing HDR metadata](replacing-inaccurate-or-missing-hdr-metadata.md)
+ [Converting the color space](converting-the-color-space.md)