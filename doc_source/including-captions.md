# Setting Up Captions in AWS Elemental MediaConvert Jobs<a name="including-captions"></a>

To include captions in your job, follow these steps in the order listed:

1. [Set the timecode source settings\.](#set-the-timecode-source-settings)

1. [Gather required captions information\.](gather-required-captions-information.md)

1. [Create input captions selectors\.](create-input-caption-selectors.md)

1. [Set up captions in outputs\.](set-up-captions-in-outputs.md)

## Specifying the Timecode Source<a name="set-the-timecode-source-settings"></a>

For your captions to correctly synchronize with your video, you must set both the input and job\-wide timecode source to **Start at 0**, or you must set both to **Embedded**\.

**Note**  
If you set both to **Embedded**, the timecodes in your captions files must begin at the same time as the timecodes that are embedded in your input video\.

**To specify values for the timecode source settings**

1. On the **Create job** page, in the **Job** pane on the left, under **Job settings**, choose **Settings**\.

1. In the **Timecode configuration ** pane, for **Source**, choose **Start at 0** or **Embedded**\.

1. On the **Create job** page, in the **Job** pane on the left, under **Inputs**, choose an input\.

1. In the **Video selector ** pane, for **Timecode source**, choose the same value that you set for **Job settings**, **Timecode configuration**\.