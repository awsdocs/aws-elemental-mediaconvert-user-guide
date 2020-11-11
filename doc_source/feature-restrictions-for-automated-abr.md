# Feature restrictions for automated ABR<a name="feature-restrictions-for-automated-abr"></a>

Jobs that include automated ABR output groups are restricted in the following ways:
+ You must use an on\-demand queue\. You can't use a reserved queue\.
+ You can enable automated ABR in jobs and job templates only\. You can't use automated ABR in output presets\.
+ In a job that includes an automated ABR output group, all ABR output groups must use automated ABR\.
+ Your output video codec must be AVC \(H\.264\) or HEVC \(H\.265\)\.
+ You must specify these required settings when you create your JSON job specification manually\. The AWS Elemental MediaConvert console sets them for you when you enable automated ABR\.
  + Set `qualityTuningLevel` to `MULTI_PASS_HQ`\.
  + Set `rateControlMode` to `QVBR`\.