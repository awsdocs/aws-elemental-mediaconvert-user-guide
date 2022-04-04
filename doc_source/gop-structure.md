# Settings for GOP structure<a name="gop-structure"></a>

When you create a job, the group of pictures \(GOP\) settings that you choose for your output affect video quality and player compatibility\. This section introduces basic GOP concepts, describes typical GOP settings, and provides guidance for choosing settings optimized for video quality\. 

A GOP is a specific arrangement of compressed video frame types\. These frame types include the following:

 **I\-Frames**   
Intra\-coded frames\. Contain all of the information a decoder uses decode the frame\. Typically, I\-frames use the most number of bits within a video stream\.

 **P\-frames**   
Predicted frames\. Contain the differences between the current frame and one or more frames before it\. P\-frames offer much better compression than I\-frames and use fewer bits within a video stream\.

 **B\-Frames**   
Bidirectional predicted frames\. Contain the differences between the current frame and one or more frames before or after it\. B\-frames offer the highest compression and take up the fewest bits within a video stream\.

A typical GOP starts with an I\-frame and follows with a repeating pattern of B\- and P\-frames\. This is a typical repeating frame pattern: IBBPBBPBBPBB

The following topics provide more information about individual GOP settings and recommend settings that are optimized for video quality\.

## GOP size<a name="gop-size-settings"></a>

GOP size \(the number of frames in a GOP\) defines the interval between I\-frames\. For example, if a GOP starts with an I\-frame and has a combination of 29 B and P\-frames, the GOP size is 30 frames\. 

A typical GOP size is 1–2 seconds long corresponding to the video frame rate\. For example, if your output frame rate is 30 frames per second, a typical GOP size is 30 or 60 frames\.

When you set your output video codec to `H_264` or `H_265`, set **GOP size** to `Auto` to allow MediaConvert to select an optimal GOP size\.

**Note**  
Streaming video formats, including HLS, DASH, CMAF, and MSS, require the fragment or segment length to be a multiple of the GOP size\. For more information, see [Setting the fragment length for streaming outputs](setting-the-fragment-length.md)\. When you set GOP size to auto for these video formats, MediaConvert automatically selects a compatible and optimized GOP size\.

## Closed GOP cadence<a name="closed-gop-cadence"></a>

Closed GOP cadence defines the number of GOPs a P\- or B\-frame is able to reference across\. A GOP can either be *open* or *closed*\. Open GOPs can have frames that reference a frame from a different GOP, while closed GOPs have frames that reference only within the GOP itself\. 

When you set your output video codec to `H_264` or `H_265`, keep **Closed GOP cadence** blank to allow MediaConvert to select an optimal closed GOP cadence\.

## Number of B\-frames between reference frames<a name="reference-frames"></a>

Defines the maximum number of B\-frames that MediaConvert can use between reference frames\.

A typical value is 1 or 2 if **GOP reference B\-Frame** is set to `Disabled`, and 3–5 if GOP reference B\-frame is set to `Enabled`\.

When you set your output video codec to `H_264`, keep **Number of B frames between reference frames** blank to allow MediaConvert to select an optimal number of B\-frames between reference frames\.

## Min I\-Interval<a name="min-i-interval"></a>

Min I\-Interval enforces a minimum number of frames between I\-frames that are created at the beginning of a GOP and I\-frames that are created by scene change detection\.

When you set your output video codec to `H_264` or `H_265`, keep **Min I\-Interval** blank to allow MediaConvert to select an optimal minimum I\-interval\.

## Settings for Adaptive Quantization<a name="adaptive-quantization"></a>

Adaptive Quantization selects the strength applied to the different quantization modes that MediaConvert uses, including flicker, spatial, and temporal quantization\. MediaConvert uses adaptive quantization to assign bits according to the complexity of your video\.

When you set your output video codec to `H_264` or `XAVC`, set **Adaptive Quantization** to `Auto` to allow MediaConvert to select an optimal adaptive quantization\.