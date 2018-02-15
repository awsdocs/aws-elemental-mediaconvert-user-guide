# Using Encryption in AWS Elemental MediaConvert<a name="using-encryption"></a>

Protect your content from unauthorized use through encryption\. Digital rights management \(DRM\) systems provide keys to AWS Elemental MediaConvert for content encryption, and licenses to supported players for decryption\.

**Note**  
To encrypt content, you must have a DRM solution provider\. To get set up, see [http://docs\.aws\.amazon\.com/speke/latest/documentation/customer\-onboarding\.html](http://docs.aws.amazon.com/speke/latest/documentation/customer-onboarding.html)\.  
The only exception to this requirement is with the Apple HLS streaming protocol, where you can choose to define your own static keys or to use a DRM provider\. 


+ [Encrypting Content](#encrypting-content)
+ [SPEKE Encryption Parameters](#speke-encryption-parameters)
+ [Static Key Encryption Parameters](#static-key-encryption-parameters)
+ [Troubleshooting Encryption](#troubleshooting-encryption)

## Encrypting Content<a name="encrypting-content"></a>

Use the following procedure to enable content encryption in **DASH ISO**, **MS Smooth**, and **Apple HLS** output groups\. To use this procedure, you should be comfortable working with output groups\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](setting-up-a-job.md#specify-output-groups)\.

**To encrypt content**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. In the navigation pane, under **Output groups**, choose the output group that you want to enable encryption for\. 

1. Below the main panel, locate and enable the **DRM Encryption** option\.

1. Follow one of these two paths, depending on your output group type: 

   + For **DASH ISO** and **MS Smooth**, fill in the encryption parameter fields\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](#speke-encryption-parameters)\.

   + For **Apple HLS**, fill in the following parameters:

     1. **Encryption method** – Choose **Sample\-AES** for Apple HLS Fairplay or **AES\-128** for Apple HLS AES\-128\. 

     1. **Key provider type** – Choose **SPEKE** to encrypt using a key provided by your DRM solution provider, or choose **Static Key** to type your own key\. 

        + For **SPEKE**, fill in the encryption parameter fields\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](#speke-encryption-parameters)\. 

        + For **Static Key**, see [[ERROR] BAD/MISSING LINK TEXT](#static-key-encryption-parameters)\.

## SPEKE Encryption Parameters<a name="speke-encryption-parameters"></a>

When you request encryption, you provide input parameters that allow the service to locate your DRM solution provider's key server, to authenticate you as a user, and to request the proper encoding keys\. This section describes the options\. Some options are available only for particular streaming protocols\. 

+ **Resource ID** – Identifier that you define for the content, which is sent to the key server to identify the current endpoint\. How unique you make this depends on how fine\-grained you want access controls to be\. The service does not allow you to use the same ID for two simultaneous encryption processes\. 

  The following example shows a resource ID:

  ```
  MovieNight20171126093045
  ```

+ **System IDs** – Unique identifiers for your streaming protocol and DRM system\. Provide up to two IDs for DASH and exactly one for the other streaming protocols\. If you provide more than one system ID, enter them on separate lines, and do not separate them with commas or any other punctuation\. For a list of common system IDs, see [DASH\-IF System IDs](http://www.dashif.org/identifiers/protection/)\. If you do not know your IDs, ask your DRM solution provider\.

+ **URL** – The URL from the API Gateway proxy that you set up to talk to your key server\. 

  The following example shows a URL: 

  ```
  https://1wm2dx1f33.execute-api.us-west-2.amazonaws.com/SpekeSample/copyProtection
  ```

### Additional Configuration Options for Apple HLS<a name="additional-encryption-parameters"></a>

+ **\(Optional\) Constant initialization vector** – A 128\-bit, 16\-byte hex value represented by a 32\-character string that is used with the key for encrypting content\.

## Static Key Encryption Parameters<a name="static-key-encryption-parameters"></a>

The following options are for static key encryption:

+ **Static key value** – A valid string for encrypting content\.

+ **URL** – The URL to include in the manifest so that content can be decrypted\.

## Troubleshooting Encryption<a name="troubleshooting-encryption"></a>

If the DRM system key server is unavailable when AWS Elemental MediaConvert requests keys, the console displays the following message: Key Server Unavailable 

Please have the following information available when contacting a support technician for troubleshooting purposes:

+ The region the job was run in

+ Job ID

+ Account ID

+ The name of your DRM solution provider

+ Any other details about the problem that you are having that might assist with troubleshooting