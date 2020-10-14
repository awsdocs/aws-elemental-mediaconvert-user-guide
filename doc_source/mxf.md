# Creating MXF outputs with AWS Elemental MediaConvert<a name="mxf"></a>

MXF is an output container format that carries video content for editing, archiving, and exchange\. The MXF format is governed by a set of specifications, some of which define *MXF profiles*, also called shims\. These MXF profiles lay out constraints on encoding settings including video codec, resolution, and bitrate\.

To make sure that your outputs comply with these specifications, you can use the MediaConvert automatic profile selection\. When you do that, MediaConvert automatically encodes the correct profile, based on the values you choose for your codec, resolution, and bitrate\. For more information, see [Default automatic selection of MXF profiles](default-automatic-selection-of-mxf-profiles.md)\.

You can also explicitly choose your MXF profile\. When you do so in the MediaConvert console, MediaConvert automatically populates the dropdown list for **Video codec** with only valid codecs\. When you aren't using automatic profile selection, refer to the relevant specifications for constraints on your resolution and bitrate\.

**Note**  
When you manually specify your MXF profile, you must set up your output in a way that is compatible with that specification\. You can submit jobs with incompatible MXF profiles and encoding settings, but those jobs will fail\.

**Topics**
+ [MXF job limitations and requirements](mxf-job-limitations.md)
+ [Setting up an MXF output](setting-up-an-mxf-job.md)
+ [Codecs supported with each MXF profile](codecs-supported-with-each-mxf-profile.md)
+ [Output audio requirements for each MXF profile](output-audio-requirements-for-each-mxf-profile.md)
+ [Default automatic selection of MXF profiles](default-automatic-selection-of-mxf-profiles.md)