# Correcting Color in the Output<a name="correcting-color-in-the-output"></a>

Set color correction as needed in each output stream's preprocessor settings\. By default, MediaConvert doesn't apply color correction\. 

In the output's stream preprocessors options, choose **Color corrector**\. Enter your values in the selections that appear\. 

**Note**  
Depending on the output type, you might need to choose the output's **More settings** options to display the preprocessors settings area\.

MediaConvert calculates color correction using the values in these fields combined with the color metadata from the input\. 

## Brightness, Contrast, Hue, and Saturation<a name="brightness-contrast-hue-saturation"></a>

Enter correction values as needed for brightness, contrast, hue, and saturation\. MediaConvert uses these settings to apply color correction independent of the other color corrector settings\. 

## Color Space Conversion<a name="color-space-conversion"></a>

Set color space conversion to encode the output stream with a different standard than the input stream\. Select the option for the format that you want to convert to\. The format that you convert from is determined by the input\.

**Supported Conversion Options**  
MediaConvert supports HDR formats, HDR 10 and HLG 2020, and SDR color spaces, Rec\. 601 and Rec\. 709, for input and output\. Your input color space is set by the input video or by your override of the input video setting\. For more information, see [Correcting Input Color Space Metadata](correcting-input-color-space-metadata.md)\.

You can't convert from HDR input to SDR output, but all other conversion options are valid\. 

The following lists the valid conversion options:
+ From any HDR format to any other HDR format \(HDR 10 or HLG 2020\)
+ From any SDR color space to any other SDR color space \(rec\. 601 and rec\. 709\)
+ From any SDR color space to any HDR format

## HDR Master Display<a name="hdr-master-display"></a>

The HDR master display information fields appear when you choose the color space conversion, Force HDR 10\. Use these fields to supply master display information metadata to be included in the output\.