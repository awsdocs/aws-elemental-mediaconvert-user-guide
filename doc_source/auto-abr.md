# Using automated ABR in AWS Elemental MediaConvert<a name="auto-abr"></a>

With automated ABR, AWS Elemental MediaConvert sets up your adaptive bitrate \(ABR\) stack for you\. MediaConvert chooses the right number of renditions and the resolution for each, based on the input video\. MediaConvert minimizes the total minutes of transcoded output by eliminating renditions that increase bitrate without providing increased video quality\. Automated ABR also maximizes video quality at various bitrates by employing the quality\-defined variable bitrate \(QVBR\) rate control mode\.

**Topics**
+ [How automated ABR works](how-automated-abr-works.md)
+ [Automated ABR frequently asked questions](automated-abr-frequently-asked-questions.md)
+ [Feature restrictions for automated ABR](feature-restrictions-for-automated-abr.md)
+ [Creating an automated ABR stack](creating-an-automated-abr-stack.md)