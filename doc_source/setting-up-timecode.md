# Setting Up Timecodes<a name="setting-up-timecode"></a>

AWS Elemental MediaConvert manages transcoded video frames by their timecode\. The service uses the timecode to synchronize some audio and captions, and to determine the timing for displaying video frames in an output\. The service also relies on timecodes to manage features—such as input clipping and graphic overlay \(image inserter\)—that are applied to only some parts of the video\.

There are three distinct groups of timecode settings, located in three different places on the console:

Job\-wide timecode configuration  
The **Timecode configuration** settings under **Job settings** affect how timecodes appear in the outputs\. The settings also affect the system behavior for features that apply to every output in the job\. This includes the following:  
+ The length of time that overlaid graphics \(inserted images\) remain on the screen
+ How your HLS variant playlists show time
+ How inserted timecodes appear in your output
+ How the service interprets the timecode that you provide if you specify an anchor timecode
If you use the API or an SDK, you can find these settings in the JSON file of your job\. These settings are under `Settings`, `TimecodeConfig`\.

Input timecode setting  
The **Timecode source** setting under **Input** affects only the following:  
+ Synchronization for audio and captions that you provide as input files that are separate from the video
+ How the service interprets the timecodes that you provide if you use [input clipping](input-clipping-stitching.md) to specify only a portion of your input for transcoding
If you use the API or an SDK, you can find this setting in the JSON file of your job, called `TimecodeSource`, located in `Settings`, `Inputs`\.

Output timecode settings  
The timecode settings under **Output** determine whether and how timecode information appears in each output:  
+ The **Timecode insertion** setting under **Output**, **Stream settings**, **Video** determines whether the service embeds timecode metadata in a given output\. You can insert timecodes into MPEG\-2, Apple ProRes, H\.264, and H\.265 outputs\.
+ The **Timecode burn\-in** settings under **Output**, **Stream settings**, **Video**, **Preprocessors** determine whether the service inscribes the timecode visually on the video frame\.

To provide frame accuracy, AWS Elemental MediaConvert uses timecodes that specify frames by frame number, not by millisecond\. All timecodes are in the following 24\-hour format with a frame number: HH:MM:SS:FF\.

**Topics**
+ [Adjusting the Job\-wide Timecode Configuration](timecode-jobconfig.md)
+ [Adjusting the Input Timecode Setting](timecode-input.md)
+ [Adjusting the Output Timecode Settings](timecode-output.md)