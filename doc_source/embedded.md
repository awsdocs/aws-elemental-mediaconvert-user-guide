# Embedded \(CEA/EIA\-608, CEA/EIA\-708\), embedded\+SCTE\-20, and SCTE\-20\+embedded<a name="embedded"></a>

If your input captions are in any of the following formats, the service handles them as "embedded":
+ CEA\-608
+ EIA\-608
+ CEA\-708
+ EIA\-708

If your input captions have both embedded captions and SCTE\-20 captions, and you want both types in your outputs, set up separate input captions selectors for the SCTE\-20 and the embedded captions tracks\. Set up the SCTE\-20 captions selectors the same way that you set up the embedded selectors\.

**Note**  
For MXF inputs, your captions are most likely on the ancillary track\. Some third\-party media analysis tools incorrectly report these captions as 608/708 embedded\. For information on setting up ancillary captions, see [QuickTime captions track or captions in MXF VANC data \(ancillary\)](ancillary.md)\.

## Number of captions selectors for embedded captions<a name="embedded-how-many-caption-selectors"></a>
+ If all of your output captions are also an embedded format, create only one captions selector, even if you want to include multiple tracks in the output\. With this setup, MediaConvert automatically extracts all tracks and includes them in the output\.
+ If all of your outputs are in a format that is not embedded, create one captions selector for each track that you want to include in the output\.
+ If some of your outputs have captions in an embedded format and some of your outputs have captions in a different format, create one captions selector for the outputs with embedded captions\. Also create individual selectors for the outputs with other captions that aren't embedded, one for each track that you want in your outputs\.

## Captions selector fields for embedded captions<a name="embedded-caption-selector-fields"></a>

**Source**: Choose **Embedded**

**CC channel number**: This field specifies the track to extract\. Complete as follows: 
+ If you are doing embedded\-to\-embedded captions \(that is, you create only one captions selector for the input embedded captions\), MediaConvert ignores this field, so keep the default value for **CC channel number**\.
+ If you are converting embedded captions to another format, \(that is, you create several captions selectors, one for each track\), specify the captions channel number from the input that holds the track that you want\. To do that, select the channel number from the dropdown list\. For example, select **1** to choose CC1\.

**Note**  
MediaConvert doesn't automatically detect which language is in each channel\. You can specify that when you set up the output captions, so that MediaConvert passes the language code metadata for the captions channel into the output for downstream use\.