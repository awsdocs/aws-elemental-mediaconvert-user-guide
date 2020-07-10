# Setting the fragment length for streaming outputs<a name="setting-the-fragment-length"></a>

For all ABR streaming output groups other than HLS \(CMAF, DASH, and Microsoft Smooth Streaming\), the value that you specify for **Fragment length** \(`FragmentLength`\) must work with the other output settings that you specify\. If you set **Fragment length** incorrectly, when viewers watch the output video, their player might crash\. This can happen because the player expects additional segments at the end of the video and requests segments that don't exist\. 

**Fragment length** is constrained by your values for **Closed GOP cadence** \(`GopClosedCadence`\), **GOP size** \(`GopSize`\), and **Framerate** \(`FramerateNumerator`, `FramerateDenominator`\)\. For information about finding these settings on the console and in your JSON job specification, see [Finding the settings related to fragment length](finding-the-settings-related-to-fragment-length.md)\.

**Note**  
When you set your output **Framerate** to **Follow source**, ensure that the framerate of your input video file \(which functions as your output framerate\) works with the value that you specify for the output **Fragment length**\.

## Rule for fragment length<a name="rule-for-fragment-length"></a>

**Fragment length** must be a whole number and must be a multiple of this value:

**GOP size** x **Closed GOP cadence** ÷ **Framerate**

## Fragment length examples<a name="fragment-length-examples"></a>

**Example: Correct settings**  
Closed GOP cadence = 1

Framerate = 30

GOP size = 60 frames

Fragment length = 2

**Example: Incorrect settings**  
Closed GOP Cadence = 1

Framerate = 50

GOP size = 90 frames

Fragment length = 2