# Transcoding Only a Portion of Your Input \(Input Clipping\)<a name="input-clipping-stitching"></a>

You can select portions of your input file \(clips\) to transcode to your outputs, excluding the rest of the input file\. When you create clips for a job, AWS Elemental MediaConvert includes the same clips in every output of the job\. If you want two outputs with different clips of the same input file, you must create two jobs and specify different input clips\.

**Note**  
To join more than one input file into a single output \(input stitching\), add another input to the job\. You can have up to 50 inputs in a job\.   
On the **Create job** page, in the **Job** section, next to **Inputs**, choose **Add**\. MediaConvert stitches together the inputs in the order that you add them\.

**To set up input clipping**

1. On the **Create job** page, in the **Job** pane on the left, choose an input\.

1. In the **Input clips** section, choose **Add input clip**\.

1. Enter the starting and ending timecodes for the first clip that you want to include\. Use the following 24\-hour format with a frame number: HH:MM:SS:FF\.

   Make sure that you provide timecodes that align with your input timecodes\. For example, if your input video has embedded timecodes that start at 01:00:00:00, you would define the start timecode for a clip thirty seconds in as 01:00:30:00, not 00:00:30:00\. 

1. If your input doesn't have embedded timecodes, change the value of the **Timecode source** for the input\. In the **Video selector** section, under **Timecode source**, choose **Start at 0**\.
**Note**  
If you change the value of **Source** in the **Timecode configuration** section of the job settings \(by choosing **Job Settings** in the **Job** pane\), it won't affect input clipping\. This setting instead affects how your output timecodes appear and how your audio and some captions formats are synchronized\.

1. Specify any additional clips by repeating steps 2 through 4 of this procedure\. Multiple clips can't overlap; each **Start timecode** must come after the previous clip's **End timecode**\.

   If you specify more than one input clip, they all appear in the output, one after the other, in the order that you specify them\.