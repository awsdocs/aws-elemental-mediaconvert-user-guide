# Setting Up an Assembly Workflow Job<a name="setting-up-an-assembly-workflow-job"></a>

Follow these steps to set up a job that combines assembly workflow features such as input clipping, input stitching, graphic overlay, and sidecar captions sync\. Doing these tasks in this order can make setup easier\. In particular, we recommend that you specify your input clips last\. This is because each input timeline counts frames from the entire input, not from each individual clip\.

This procedure relies on the concept of input and output timelines\. For more information, see [How MediaConvert Uses Timelines to Assemble Jobs](how-mediaconvert-uses-timelines-to-assemble-jobs.md)\.

**To set up an assembly workflow job \(console\)**

1. **Specify your video input files\.**

   You can have up to 150 inputs in a job\. MediaConvert stitches together the inputs in the order that you add them\. If you want to use multiple clips from the same input file, and you want them in chronological order without other inputs in between them, specify the input file only once\.

   For full instructions, see [Step 1: Specify Your Input Files](specify-input-settings.md)\.

1. **Set up your audio selectors\.**

   In each input, you create audio selectors to map your input audio to your outputs\. For instructions, see [Step 2: Create Input Selectors for Video, Audio, and Captions](create-selectors.md)\.

   With sidecar audio files, MediaConvert synchronizes audio and video without regard to timecodes\. MediaConvert lines up the start of the audio file with the start of the video file\.

   Whether your audio is in a sidecar file or is embedded in the video, you can adjust its sync using the **Offset** setting in the input audio selector\. Use a positive number for **Offset** to move the audio later in the input timeline; use a negative number to move it earlier\.

1. **Synchronize any sidecar captions\.**

   How you set up your sidecar captions sync depends on the input captions format:
   + If your input captions format is timecode\-based \(for example, SCC or STL\), the service synchronizes the timecode in the captions file with the input timeline\.
   + If your input captions format is timestamp\-based \(for example, SRT, SMI, or TTML\), the service synchronizes the captions with the video without regard to timecodes\.

**Related information**
   + [About Input Timecode Source and Captions Alignment](about-input-timecode-source-and-captions-alignment.md)
   + [Adjusting the Input Timeline with the Input Timecode Source](timecode-input.md)
   + [Setting Up Captions](including-captions.md) 

1. **Set up when you want any graphic overlays or motion graphic overlays to appear\.**

   How you specify the time that the overlay appears depends on what kind of overlay you specify:
   + For input still graphic overlays, specify the overlay in the input where you want the overlay to appear\. Specify the start and end times with timecodes that match with that input's timeline\.
   + For output still graphic overlays, specify when you want the overlay to appear based on the output timeline\.
   + For motion graphic overlays, specify when you want the overlay to appear based on the inputs' timelines\.

**Related information**
   + [Adjusting the Input Timeline with the Input Timecode Source](timecode-input.md)
   + [Adjusting the Output Timeline with the Job\-wide Timecode Configuration](timecode-jobconfig.md)
   + [Using Image Inserter \(Graphic Overlay\)](graphic-overlay.md)

1. **Specify input clips\.**

   Unless you want MediaConvert to include the full duration of the input, specify input clips for each input\. Specify the start and end times with timecodes that match with that input's timeline\.

   Set up input clips as follows:

   1. On the **Create job** page, in the **Job** pane on the left, choose an input\.

   1. In the **Input clips** section, choose **Add input clip**\.

   1. Enter the starting and ending timecodes for the first clip that you want to include\. Use the following 24\-hour format with a frame number: HH:MM:SS:FF\.

      Make sure that you provide timecodes that align with your input timeline\. For more information, see [Adjusting the Input Timeline with the Input Timecode Source](timecode-input.md)\.

   1. Specify any additional clips\. Multiple clips must be in chronological order and can't overlap; each **Start timecode** must come after the previous clip's **End timecode**\.

      If you specify more than one input clip, they all appear in the output, one after the other, in the order that you specify them\.