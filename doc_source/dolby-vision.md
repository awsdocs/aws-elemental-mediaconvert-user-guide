# Creating Dolby Vision outputs with AWS Elemental MediaConvert<a name="dolby-vision"></a>

Dolby Vision video uses an extended color palette and contrast range with dynamic, per\-frame metadata\. With AWS Elemental MediaConvert, you can create Profile 5 or Profile 8\.1 Dolby Vision outputs from supported sources\.

## Set up a Dolby Vision job<a name="setting-up-a-dolby-vision-job"></a>

Use the following steps to set up a Dolby Vision job\. For more information about jobs, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. For your input file or files, choose from the following:

   1. MXF file with frame\-interleaved Dolby Vision metadata or an XML file\.

   1. IMF package \(IMP\) with frame\-interleaved Dolby Vision metadata or an XML file\. Also, specify a composition playlist \(CPL\) file for your input\. If your CPL is from an incomplete IMP, choose **Supplemental IMPs** to specify the location of your supplemental IMPs\.

   1. Apple ProRes QuickTime MOV with a Dolby Vision studio metadata XML file\.

   1. Any input with an HDR10 YUV color space\.

1. For each output that you want to process with Dolby Vision, do the following:
   + Make sure that your output settings conform to the limitations listed in [Dolby Vision input format support and job setting requirements](#dolby-vision-job-limitations-and-requirements)\.
   + Enable the **Dolby Vision** preprocessor\.
   + Specify a Dolby Vision **Profile** from one of the following choices:
     + **Profile 5**: Includes frame\-interleaved Dolby Vision metadata in your output\.
     + **Profile 8\.1**: Includes both frame\-interleaved Dolby Vision metadata and HDR10 metadata in your output\.

1. Choose an on\-demand queue\. Your default queue is on\-demand\.

## Dolby Vision input format support and job setting requirements<a name="dolby-vision-job-limitations-and-requirements"></a>

The tables in this section describe Dolby Vision input format support and job setting requirements for implementation with AWS Elemental MediaConvert\.

The following table describes input format requirements for Dolby Vision Profile 5 or Profile 8\.1 outputs\.


| Dolby Vision Profile | Supported inputs with Dolby Vision metadata | Supported inputs without Dolby Vision metadata | 
| --- | --- | --- | 
| Profile 5 |  IMF, MXF [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/dolby-vision.html) QuickTime \(\.mov\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/dolby-vision.html)  |  HDR10 [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/dolby-vision.html)  | 
| Profile 8\.1 |  IMF, MXF [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/dolby-vision.html) QuickTime \(\.mov\) [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/dolby-vision.html)  | None | 

The following table describes feature limitations and job requirements for Dolby Vision outputs\.


| Feature | Job setting requirement | 
| --- | --- | 
| Dolby Vision Profile 8\.1 output | Maximum one input videoMaximum one input clip | 
| Queue type |  **On\-demand queue**  | 
| Input Frame rate | All inputs must have the same frame rate\. Frame rate conversion is not supported\. | 
| Output Frame rate | Follow source \(default setting\) | 
| Image inserter | Disabled \(default setting\) | 
| Motion image inserter | Disabled \(default setting\) | 
| Output Video codec | HEVC \(H\.265\) | 
| Output Color metadata | Insert \(default setting\) | 
| Respond to AFD | None \(default setting\) | 
| Output video Resolution \(w x h\) | Maximum width: 4096Maximum height: 4096 | 
| Output video codec Profile | Main10/Main or Main10/High | 
| Color corrector preprocessor | Disabled \(default setting\) | 
| Timecode burn\-in preprocessor | Disabled \(default setting\) | 
| Noise reducer preprocessor | Disabled \(default setting\) | 
| Output captions Destination type | Burn\-in captions are not supported\. | 