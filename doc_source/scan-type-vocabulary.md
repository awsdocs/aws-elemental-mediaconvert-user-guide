# Basic scan type vocabulary<a name="scan-type-vocabulary"></a>

Progressive video  
*Progressive video* includes all lines in all frames\. It looks better on modern screens because it drastically reduces the amount of image flicker the viewer sees on the screen\. Devices displaying progressive video will re\-draw all horizontal lines in a frame\. For example, a device running at 50 Hertz playing a 1080 progressive video re\-draws 1080 lines \(every line in the frame\) 50 times per second\.

Interlaced video  
*Interlaced video* uses a technique that doubles the perceived frame rate of a video display without consuming extra bandwidth\. On older displays, most people won't notice decreased video quality with interlaced video\. Devices that support interlaced video re\-draw every *other* horizontal line in a frame\. For example, a device running at 50 Hertz playing a 1080 interlaced video redraws 540 lines \(half of the lines in the frame\) 50 times per second\. 

Field polarity for interlaced frames  
Interlaced video contains two fields of a video frame, each one made up of every other horizontal line the image\. *Field polarity* in video distinguishes between these two sets of lines\. A set's polarity indicates whether the top field comes first or bottom field comes first\. In the following illustration, the set with top field polarity is shown in blue and contains the topmost line\. The set with bottom field polarity is shown in red and contains the second horizontal line from the top\. The complete frame contains both, with each set being refreshed alternately\.  

![\[The illustration representing the complete frame is a square made up of alternating blue and red stripes. The top field square shows only the blue stripes, with white representing space between them. The first blue stripe is at the top of the square. The bottom field square shows only the red stripes. The first red stripe is one stripe's width below the top.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/interlaced-field.PNG)
When you create interlaced outputs with MediaConvert, you can specify which field polarity comes first with the setting **Interlace mode**\.