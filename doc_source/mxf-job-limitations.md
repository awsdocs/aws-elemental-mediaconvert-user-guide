# MXF job limitations and requirements<a name="mxf-job-limitations"></a>

MediaConvert restricts MXF jobs in these ways:
+ You can put MXF outputs in a **File group** output group only\.
+ You must choose a video codec that is supported with your MXF profile\. The following table details which codecs are supported with each profile\. For more information, see [Codecs supported with each MXF profile](codecs-supported-with-each-mxf-profile.md)\.
+ You must set up your output audio tracks according to the requirements of the MXF profile\. This applies whether you specify the profile or have MediaConvert automatically select it for you\. For more information, see [Output audio requirements for each MXF profile](output-audio-requirements-for-each-mxf-profile.md)\.