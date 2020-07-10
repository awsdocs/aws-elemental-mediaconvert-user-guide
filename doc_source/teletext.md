# Teletext<a name="teletext"></a>

You can use teletext captions in one of the following ways:
+ Teletext can include more data than just captions\. If you want to include the entire teletext input, your input and output captions format must be teletext\. You can't convert the entire set of teletext data to another captions format\. 

  MediaConvert supports teletext\-to\-teletext only in MPEG\-2 outputs\.
+ You can extract and convert individual captions pages to another captions format\. You can't extract individual captions pages and keep them in teletext format\. If you want to extract individual captions pages, you must convert them to another format\.

## Number of captions selectors for teletext<a name="how-many-caption-selectors-2"></a>
+ If you are doing teletext\-to\-teletext captions, create only one captions selector, even if you want to include multiple tracks in the output\. In this case, MediaConvert automatically extracts all tracks and includes them in the output\. 
+ If you are doing teletext\-to\-other, create one captions selector for each track that you want to include in the output\.
+ If you are doing teletext\-to\-teletext in some outputs and teletext\-to\-other in other outputs, create one captions selector for the teletext\-to\-teletext, and then create individual selectors for the teletext\-to\-other, one for each track that MediaConvert converts\.

## Captions selector fields for teletext captions<a name="caption-selector-fields-teletext"></a>
+ **Source**: Choose **Teletext**\.
+ **Page**: This field specifies the captions page that you want\. Complete as follows: 
  + If you are doing teletext\-to\-teletext captions \(that is, you create only one captions selector for the input embedded captions\), keep this field blank\. MediaConvert ignores any value that you provide\.
  + If you are converting teletext to another format \(that is, you create several captions selectors, one for each output captions track you want to create\), then specify the captions page that you want for each selector\. If you keep this field blank, you will get a validation error when you submit the job\. 