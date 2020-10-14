# Working with video frame rates in AWS Elemental MediaConvert<a name="working-with-video-frame-rates"></a>

The *frame rate* of a video asset represents how quickly video player devices play back the frames of a video, in frames per second \(fps\)\. For example, films have a frame rate of 24 fps, NTSC television broadcasts are 29\.97/59\.94 fps, and PAL television broadcasts are 50/25 fps\. If you keep the MediaConvert default settings in your job, your output video will have the same frame rate as your input video\.

Some videos have a frame rate that varies over the duration of the video\. For example, some cameras automatically generate video that uses more frames for high\-action sequences and fewer frames for sequences with less motion\. MediaConvert supports variable frame rate \(VFR\) inputs, but creates only constant frame rate \(CFR\) outputs\. For more information, see [Using variable frame rate inputs](using-variable-frame-rate-inputs.md)\.

**Topics**
+ [Settings for frame rate conversion](settings-for-frame-rate-conversion.md)
+ [Using variable frame rate inputs in AWS Elemental MediaConvert](using-variable-frame-rate-inputs.md)
+ [Converting the frame rate of your video](converting-frame-rate.md)