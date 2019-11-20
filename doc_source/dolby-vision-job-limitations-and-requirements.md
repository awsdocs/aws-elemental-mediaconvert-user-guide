# Dolby Vision Job Limitations with AWS Elemental MediaConvert<a name="dolby-vision-job-limitations-and-requirements"></a>

Note the following restrictions and requirements in the AWS Elemental MediaConvert implementation of Dolby Vision:

Job limitations:
+ You can create only Dolby Vision profile 5 outputs\.
+ You can send Dolby Vision jobs only to on\-demand queues\. You can't send them to reserved queues\.
+ You must keep the **Motion image inserter** global processor disabled\.

Input requirements:
+ Your input format must be IMF or MXF\.
+ Your input must contain frame\-interleaved Dolby Vision metadata\.
+ All of your inputs must have the same frame rate\. Frame rate conversion is not supported\.
+ You must keep **Image inserter** disabled\.

Output settings:
+ You must set **Video codec** to HEVC \(H\.265\)\.
+ Your output container must be supported with the HEVC \(H\.265\) codec, as listed in [Supported Output Codecs and Containers](reference-codecs-containers.md)\.
+ For **Color metadata**, you must keep the default setting **Insert**\.
+ For **Respond to AFD**, you must keep the default setting **None**\.
+ For **Frame rate**, you must keep the default setting **Follow source**\. Frame rate conversion is not supported\.
+ You must set the codec **Profile** to either **Main10/Main** or **Main10/High**\.
+ You must keep the **Image inserter** preprocessor disabled\.
+ You must keep the **Color corrector** preprocessor disabled\.
+ You must keep the **Timecode burn in** preprocessor disabled\.
+ You must keep the **Noise reducer** preprocessor disabled\.
+ You must choose an output captions format other than **Burn in**\.