# Burn\-in output captions<a name="burn-in-output-captions"></a>

Burn\-in is a delivery method rather than a captions format\. Burn\-in writes the captions directly on your video frames, replacing pixels of video content with the captions\. If you want burn\-in captions in an output, set the captions up according to the following information\.

## Where to specify the captions<a name="where-burn-in-output-captions"></a>

Put your captions in the same output group and the same output as your video\.

## How to specify multiple captions tracks<a name="multilang-burn-in-output-captions"></a>

You can burn in only one track of captions in each output\.

## How to specify the font script<a name="how-to-specify-the-language-script-burnin"></a>

AWS Elemental MediaConvert automatically selects the appropriate script for your captions, based on the language that you specify in the output captions settings\. If the language that you choose has more than one possible script, specify the script that you want\.

**To ensure that the service uses the correct font script**

1. In the **Captions** section under **Encoding settings**, for **Language**, choose the language of the captions text\.

1. If the language that you specify has more than one possible script, use **Font script** to specify the script\.

   For example, if you choose **Chinese** \(ZH\) for **Language**, use **Font script** to choose either **Simplified Chinese** or **Traditional Chinese**\. In this case, if you don’t specify a value for **Font script**, the service defaults to simplified Chinese\. 
**Tip**  
In most cases, for **Font script** you can keep the default value of **Automatic**\. When you do, the service chooses the script based on the language of the captions text\.