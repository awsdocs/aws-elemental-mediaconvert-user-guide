# QuickTime captions track or captions in MXF VANC data \(ancillary\)<a name="ancillary"></a>

If your input captions are in either of the following formats, the service handles them as "ancillary" data:
+ QuickTime captions track \(format QTCC\)
+ MXF VANC data

MediaConvert does not create output captions in these formats, but you can convert them to a [supported output format](captions-support-tables-by-container-type.md)\.

**For ancillary captions**
+ Create one captions selector per track that you will use in your outputs\.
+ In each captions selector, for **Source**, choose **Ancillary**\.
+ In each captions selector, for **CC channel**, choose the channel number for the track that is associated with the selector\.

  For example, the input captions have English in CC channel 1 and Spanish in CC channel 2\. To use these captions, create Captions selector 1, and then choose 1 in the **CC channel** dropdown list\. Next, create Captions selector 2, and then choose 2 in the **CC channel** dropdown list\.