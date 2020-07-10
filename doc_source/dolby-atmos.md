# Creating Dolby Atmos outputs with AWS Elemental MediaConvert<a name="dolby-atmos"></a>

Dolby Atmos provides an immersive audio experience in cinemas and home theaters\. With the right audio input files, you can use AWS Elemental MediaConvert to create Dolby Atmos outputs\. You can create streaming outputs that end viewers can experience in their home theaters or file outputs that you can use in your professional workflows\.

AWS Elemental MediaConvert can create Dolby Digital Plus with Atmos outputs by either encoding channel\-based immersive audio content that you provide as 9\.1\.6 PCM mono channels, or by passing through already encoded Dolby Digital Plus with Atmos content\.

**Note**  
MediaConvert doesn't support ADM or DAMF input\.

**Topics**
+ [Using Dolby Atmos passthrough with AWS Elemental MediaConvert](using-dolby-atmos-passthrough.md)
+ [Using Dolby Atmos encoding with AWS Elemental MediaConvert](using-dolby-atmos-encoding.md)