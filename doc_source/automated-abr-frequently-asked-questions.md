# Automated ABR frequently asked questions<a name="automated-abr-frequently-asked-questions"></a>

**How can I see what renditions AWS Elemental MediaConvert created for me?**  
You can see the properties of the outputs in your ABR stack in these places:
+ The job completion event from Amazon CloudWatch Events\. For more information, see [Using CloudWatch Events with AWS Elemental MediaConvert](cloudwatch_events.md)\.
+ The **Job summary** page on the MediaConvert console\. For more information, see [Viewing your AWS Elemental MediaConvert job history](viewing-job-history.md)\.

**Will my automated ABR job take a long time to run?**  
We recommend that you always use [accelerated transcoding](accelerated-transcoding.md) with automated ABR\. When you do, your job should take only slightly longer than an accelerated transcoding job for a manually specified ABR stack with similar outputs\. You don't pay more for enabling accelerated transcoding because automated ABR is already billed at the 2 Pass \(Quality Optimized\) professional tier rate\.

When you run an automated ABR job without accelerated transcoding, it takes much longer to run than a job with a manually specified ABR stack with similar outputs\.\.

**Why do some of my output renditions have the same resolution?**  
When display devices stream an ABR asset, they request segments based on the bitrate of the rendition, not based on the resolution of the rendition\. Therefore, an ABR stack can have renditions for different bandwidths that have the same resolution\. The higher bandwidth rendition will have better quality at the same resolution\.

Whether increasing the resolution improves video quality when you go up to the next rendition of the stack depends on the complexity of the video\. The ability to automatically adjust these choices on a per\-job basis is one of the ways that this feature gives you better results with less effort\.

**Can I tell ahead of time how many renditions will be in my stack?**  
No\. MediaConvert determines which renditions to use during the transcoding process\. Because the encoding decisions depend on qualities of your input video, there's no way to know before running the job what those decisions will be\.

You can use the optional limits settings to make sure that the number of renditions, and the size of those renditions, won't exceed what you want\.

**How will I be billed for an automated ABR stack?**  
MediaConvert bills you for only the renditions that it writes to your output location\. For example, you might set **Max renditions** to 12, but MediaConvert might determine that there is no advantage to creating more than eight renditions\. In this case, MediaConvert would bill you for only eight renditions\.

Automated ABR is a professional\-tier feature and also requires 2 pass encoding\.  Every rendition is billed per\-minute at the 2 Pass \(Quality Optimized\) rate\. For example, say your automated ABR stack ends up with 10 renditions, each of them being 60 minutes long\. You would then be charged for 600 minutes\. For rates, see [AWS Elemental MediaConvert Pricing](https://aws.amazon.com/mediaconvert/pricing/) in the *AWS Cloud Products* website\.

**What about audio?**  
Automated ABR does the set up for your video renditions only\. You add audio renditions as audio\-only outputs inside of your automated ABR output group\. For instructions, see [Creating an automated ABR stack](creating-an-automated-abr-stack.md)\.

**What about captions?**  
Add captions to your automated ABR package as captions\-only output\. For instructions, see [Creating an automated ABR stack](creating-an-automated-abr-stack.md)\.