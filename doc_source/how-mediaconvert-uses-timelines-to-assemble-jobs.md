# How MediaConvert uses timelines to assemble jobs<a name="how-mediaconvert-uses-timelines-to-assemble-jobs"></a>

MediaConvert assembles inputs and input clips according to *input timelines* and the *output timeline*\. The service constructs these timelines based on your settings, and then assembles your inputs into outputs based on them\. The following illustration shows three independent input timelines and an output timeline\.

![\[Three separate input files are represented with three rectangles. Each is marked with a number line that represents an input timeline. One timeline starts at zero. One timeline shows embedded timecodes. One timeline reflects a specified start setting that starts at one hour. Two of these rectangles have clips inside them, represented with color fill in only parts of the rectangle. One of the rectangles is filled entirely, representing that the entire input file is used in the output. Below the input rectangles is a wider rectangle that represents all the clips and inputs assembled together. This rectangle is marked with a number line that represents the output timeline, which starts at 00:00:00:00.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/assembly.png)

**Topics**
+ [Input timelines](input-timelines.md)
+ [Output timeline](output-timeline.md)