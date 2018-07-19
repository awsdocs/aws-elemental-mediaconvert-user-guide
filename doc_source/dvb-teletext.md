# Teletext<a name="dvb-teletext"></a>

You can use teletext captions in one of the following ways:
+ Teletext can include more data than just captions\. If you want to include the entire teletext input, your input and output captions format must be teletext\. You can't convert the entire set of teletext data to another captions format\. 

  AWS Elemental MediaConvert supports teletext\-to\-teletext only in MPEG\-2 outputs\.
+ You can extract and convert individual captions pages \(that is, the captions in a specific language\) to another captions format\. You can't extract individual captions pages and keep them in teletext format\. If you want to extract individual captions pages, you must convert them to another format\.

## Number of Captions Selectors for Teletext<a name="how-many-caption-selectors-2"></a>
+ If you are doing teletext\-to\-teletext captions, create only one captions selector, even if you want to include multiple languages in the output\. In this case, AWS Elemental MediaConvert automatically extracts all languages and includes them in the output\. 
+ If you are doing teletext\-to\-other, create one captions selector for each language that you want to include in the output\.
+ If you are doing teletext\-to\-teletext in some outputs and teletext\-to\-other in other outputs, create one captions selector for the teletext\-to\-teletext, and then create individual selectors for the teletext\-to\-other, one for each language that AWS Elemental MediaConvert converts\.

## Captions Selector Fields for Teletext Captions<a name="caption-selector-fields-teletext"></a>
+ **Source**: Choose **Teletext**\.
+ **Page**: This field specifies the page of the language that you want\. Complete as follows: 
  + If you are doing teletext\-to\-teletext captions \(that is, you create only one captions selector for the input embedded captions\), keep this field blank\. AWS Elemental MediaConvert ignores any value that you provide\.
  + If you are converting teletext to another format \(that is, you create several captions selectors, one for each language\), then specify the page for the language that you want\. If you keep this field blank, you will get a validation error when you submit the job\. 