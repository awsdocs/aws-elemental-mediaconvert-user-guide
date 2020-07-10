# Step 3: Create output groups<a name="specify-output-groups"></a>

After specifying your input, create output groups\. The choices that you make when you set up output groups affect the types of assets that your job produces and which devices can play them\. The following illustration shows the two categories of output groups and how outputs and selectors are organized within them\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_output-groups.png)

As shown in the preceding illustration, you can use AWS Elemental MediaConvert to create media assets that fall broadly into two categories:
+ **ABR streaming packages**\. You can create adaptive bitrate \(ABR\) packages to allow end viewers to download the asset a little at a time while they watch\. Depending on how you set up your outputs, the end viewer's device can adapt to changes in the available bandwidth by downloading higher\- or lower\-quality segments\. ABR packages are also called ABR *stacks*, because they are made up of a "stack" of video, audio, and captions components\. Each component in the stack or package is called a *rendition*\.
+ **Standalone files**\. You might create these files and host them in a location where end viewers download the entire file all at once and then view it\. You might also create standalone files and then send them to downstream systems for packaging and distribution\.

**To create an output group**

1. In the **Job** pane, in the **Output groups** section, choose **Add**\.

1. Choose an output group type, and then choose **Select**\. Create one file output group for all the standalone files that you intend to create\. Create one ABR streaming output group for each ABR streaming package that you intend to create\. For guidance on which ABR streaming output groups to include in your job, see [Choosing your ABR streaming output groups](choosing-your-streaming-output-groups.md)\.

1. Optionally, for **Custom group name**, enter a name for your group\. Any name that you provide here appears in the **Output groups** section of the console but does not affect your outputs\.

1. For **Destination**, specify the URI for the Amazon S3 location where the transcoding service will store your output files\. You can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\.
**Note**  
You can optionally append a basename to your destination URI\. To create the file name of your final asset, the transcoding service uses this basename along with any name modifier that you provide in the individual output settings\.  
If you don't provide a basename with your URI, the transcoding service generates a basename from the Input 1 file name, minus the extension\.

1. Specify the values for any additional settings that apply to the entire output group\. These settings vary depending on the type of output group that you select\. For more information about individual settings, choose the **Info** link next to each setting\.