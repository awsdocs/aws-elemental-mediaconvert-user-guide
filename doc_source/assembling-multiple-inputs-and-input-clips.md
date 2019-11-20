# Assembling Multiple Inputs and Input Clips with AWS Elemental MediaConvert<a name="assembling-multiple-inputs-and-input-clips"></a>

You can use MediaConvert for *assembly workflows*\. An assembly workflow is a MediaConvert job that performs basic input clipping and stitching to assemble output assets from different sources without requiring separate editing software\. For example, an assembly workflow might put together a bumper followed by feature content that is interleaved with advertisements\. The feature content might have a logo graphic overlay at the beginning of each feature segment\.

With these kinds of jobs, you assemble your outputs from multiple inputs \(using *input stitching*\) or portions of inputs \(using *input clipping*\)\. MediaConvert creates all the outputs of a job from this assembly\. If you want outputs with different clips of the input files or with different arrangements of the inputs, you must create a separate job for each assembly\.

**Topics**
+ [How MediaConvert Uses Timelines to Assemble Jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)
+ [Setting Up an Assembly Workflow Job](setting-up-an-assembly-workflow-job.md)
+ [Setting Up Timecodes](setting-up-timecode.md)