# Setting up timecodes<a name="setting-up-timecode"></a>

MediaConvert manages transcoded video frames by their timecode\. The service uses the timecodes from the input and output timelines that it constructs to line up the elements of your output assets\. For information about which features are affected by each type of timeline, and about how timelines work, see [How MediaConvert uses timelines to assemble jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\.

There are three distinct groups of timecode settings, located in three different places on the console:
+ Input timecode settings

  The input setting **Timecode source** affects the input timeline\.
+ Job\-wide timecode configuration

  The **Timecode configuration** settings under **Job settings** affect the output timeline\.
+ Output timecode settings

  The timecode settings under **Output** determine whether and how timecode information appears in each output\. These settings affect only what is included in the outputs; they don't determine what timecodes are\.

To provide frame accuracy, AWS Elemental MediaConvert uses timecodes that specify frames by frame number, not by millisecond\. All timecodes are in the following 24\-hour format with a frame number: HH:MM:SS:FF\. For drop frame, MediaConvert uses a semicolon before the frame number: HH:MM:SS;FF\.

**Topics**
+ [Adjusting the input timeline with the input timecode source](timecode-input.md)
+ [Adjusting the output timeline with the job\-wide timecode configuration](timecode-jobconfig.md)
+ [Putting timecodes in your outputs](timecode-output.md)