# Setting Up Captions in Outputs<a name="set-up-captions-in-outputs"></a>

The location of the captions in a job depends on your output captions format: Your captions might be in the same output as your video, a separate output in the same output group as your video, or in an entirely separate output group\. How you set up multiple captions tracks also depends on the output captions format\. The following procedure shows how to set up captions for different outputs\. 

**To set up captions for different outputs**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. Create input captions selectors as described in [Creating Input Captions Selectors](create-input-caption-selectors.md)\.

1. Determine where in your job to specify the captions\. This choice depends on the output captions format\. Consult the relevant topic below to look this up\.

1. In the left pane of the **Create job** page, choose the appropriate output from the list of outputs\.

1. Under **Encoding settings**, choose **Add caption**\. This displays a captions settings area under **Encoding settings**\. 

1. If your output captions format requires a separate group of captions settings for each track in the output, choose **Add captions** again until you have one captions group for each track\. To determine whether you need one captions settings group for all tracks or one for each track, see the relevant topic below\.

1. Under **Encoding settings**, choose **Captions 1** from the list\.

1. Under **Captions source**, choose a captions selector\. This selects the track or tracks that you associated with the selector when you set up your input, so that AWS Elemental MediaConvert will include those captions in this output\.

1. Under **Destination type**, choose an output captions format\. Check [Captions Support Tables by Output Container Type](captions-support-tables-by-container-type.md) to ensure that you are choosing a supported format\.

1. Provide values for any additional fields as described in the relevant topic below\.

**Topics**
+ [TTML and WebVTT \(ABR\) Output Captions](ttml-and-webvtt-output-captions.md)
+ [CEA/EIA\-608 and CEA/EIA\-708 \(Embedded\) Output Captions](embedded-output-captions.md)
+ [DVB\-Sub Output Captions](dvb-sub-output-captions.md)
+ [SCC, SRT \(Sidecar\) Output Captions](scc-srt-output-captions.md)
+ [Teletext Output Captions](teletext-output-captions.md)
+ [Burn\-In Output Captions](burn-in-output-captions.md)