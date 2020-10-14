# Working with progressive and interlaced scan types in AWS Elemental MediaConvert<a name="working-with-scan-type"></a>

*Progressive* and *interlaced* are two types of video display methods\. Modern display devices detect whether a video is interlaced or progressive and automatically  play back the video correctly\. But, progressive video looks much better on modern screens\.

To get the best results with using interlacing/deinterlacing and converting to and from telecine, you must consider how your input video was recorded and what transformations have been done to it\. For example, when you apply deinterlacing to an input that is not interlaced, your output video quality suffers\.

**Topics**
+ [Basic scan type vocabulary](scan-type-vocabulary.md)
+ [Settings for scan type conversion](settings-for-scan-type-conversion.md)
+ [Valid settings combinations](valid-settings-combinations.md)
+ [Converting the scan type of your video](converting-scan-type.md)