# Using variable frame rate inputs in AWS Elemental MediaConvert<a name="using-variable-frame-rate-inputs"></a>

Some videos have a frame rate that varies over the duration of the video\. Some cameras—for example, the cameras in many smartphones—automatically generate video that uses more frames for high\-action sequences and fewer frames for sequences with less motion\. MediaConvert supports variable frame rate \(VFR\) inputs, but creates only constant frame rate \(CFR\) outputs\.

The default setting for output frame rate is **Follow source**\. **Follow source** causes different behavior depending on whether your input video has a constant or variable frame rate\.
+ For constant frame rate inputs, **Follow source** results in outputs that have the same frame rate as the input video\.
+ For variable frame rate inputs, **Follow source** results in outputs that have a constant frame rate output, with a frame rate that is the average of the input frame rates, rounded up to the nearest whole number standard frame rate: 1, 5, 10, 15, 24, 30, 50, or 60 fps\.

**Feature restrictions**  
MediaConvert support for variable frame rate video is limited in these ways:
+ Variable frame rates are supported as input only\. Outputs are only constant frame rate\.
+ Variable frame rate inputs are supported in these containers only: MP4, MOV, WEBM, and MKV\.