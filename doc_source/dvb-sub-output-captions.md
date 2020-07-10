# DVB\-Sub output captions<a name="dvb-sub-output-captions"></a>

## Where to specify the captions<a name="where-dvb-sub-output-captions"></a>

Put your captions in the same output group and the same output as your video\.

## How to specify multiple captions tracks<a name="multilang-dvb-sub-output-captions"></a>
+ If your input captions are the same format as your output captions \(passthrough\), you need to create only one group of captions settings\. The captions selector that you choose under **Captions source** includes all tracks from the input\.
+ If your input captions are in a different format, create one group of captions settings for each track\. Put each group of captions settings in the same output\. They will appear in the list of settings groups as Captions 1, Captions 2, and so forth\. In each group of settings, choose the captions selector under **Captions source** that is set up for the track that you want to include\.

## How to specify the font script<a name="how-to-specify-lang-script-dvb-sub"></a>

AWS Elemental MediaConvert automatically selects the appropriate script for your captions, based on the language that you specify in the output captions settings\. If the language that you choose has more than one possible script, specify the script that you want\.

**To ensure that the service uses the correct font script**

1. In the **Captions** section under **Encoding settings**, for **Language**, choose the language of the captions text\.

1. If the language that you specify has more than one possible script, use **Font script** to specify the script\.

   For example, if you choose **Chinese** \(ZH\) for **Language**, use **Font script** to choose either **Simplified Chinese** or **Traditional Chinese**\. In this case, if you don’t specify a value for **Font script**, the service defaults to simplified Chinese\. 
**Tip**  
In most cases, for **Font script** you can keep the default value of **Automatic**\. When you do, the service chooses the script based on the language of the captions text\.