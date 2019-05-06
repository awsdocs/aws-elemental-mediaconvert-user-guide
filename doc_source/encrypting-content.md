# Encrypting Content<a name="encrypting-content"></a>

Use the following procedure to enable content encryption in **DASH ISO**, **MS Smooth**, and **Apple HLS** output groups\. To use this procedure, you should be comfortable working with output groups\. For more information, see [Step 3: Create Output Groups](specify-output-groups.md)\.

**To encrypt content**

1. Open the AWS Elemental MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. In the navigation pane, under **Output groups**, choose the output group that you want to enable encryption for\. 

1. Below the main pane, locate and enable the **DRM encryption** option\.

1. Follow one of these two paths, depending on your output group type: 
   + For **DASH ISO** and **MS Smooth**, fill in the encryption parameter fields\. For more information, see [SPEKE Encryption Parameters](#speke-encryption-parameters)\.
   + For **Apple HLS**, fill in the following parameters:
     + For **Encryption method**, choose **Sample\-AES** for Apple HLS FairPlay or choose **AES\-128** for Apple HLS AES\-128\. 
     + **Key provider type** – Choose **SPEKE** to encrypt using a key provided by your DRM solution provider, or choose **Static key** to enter your own key\. 
       + For **SPEKE**, fill in the encryption parameter fields\. For more information, see [SPEKE Encryption Parameters](#speke-encryption-parameters)\. 
       + For **Static Key**, see [Static Key Encryption Parameters](#static-key-encryption-parameters)\.

## SPEKE Encryption Parameters<a name="speke-encryption-parameters"></a>

When you request encryption, you provide input parameters that allow the service to locate your DRM solution provider's key server, to authenticate you as a user and to request the proper encoding keys\. Some options are available only for particular streaming protocols\.

Enter the SPEKE encryption parameters as follows: 
+ For **Resource ID**, enter an identifier for the content\. The service sends this to the key server to identify the current endpoint\. How unique you make this depends on how fine\-grained you want access controls to be\. The service does not allow you to use the same ID for two simultaneous encryption processes\. The resource ID is also known as the content ID\. 

  The following example shows a resource ID:

  ```
  MovieNight20171126093045
  ```
+ For **System IDs**, enter unique identifiers for your streaming protocol and DRM system\. Provide up to two IDs for DASH and exactly one for the other streaming protocols\. If you provide more than one system ID, enter them on separate lines, and do not separate them with commas or any other punctuation\. For a list of common system IDs, see [DASH\-IF System IDs](https://dashif.org/identifiers/content_protection/)\. If you do not know your IDs, ask your DRM solution provider\.
+ For **URL**, enter the URL of the API Gateway proxy that you set up to talk to your key server\. The API Gateway proxy must reside in the same AWS Region as MediaConvert\.

  The following example shows a URL: 

  ```
  https://1wm2dx1f33.execute-api.us-west-2.amazonaws.com/SpekeSample/copyProtection
  ```
+ \(Optional\) For **Certificate ARN**, enter a 2048 RSA certificate ARN to use for content key encryption\. Use this option only if your DRM key provider supports content key encryption\. If you use this and your key provider doesn't support it, the request fails\.

  To enter a certificate ARN here, you must have already imported the corresponding certificate into AWS Certificate Manager, entered the certificate ARN from ACM into the MediaConvert **Certificates** pane, and associated it with MediaConvert\. For more information, see [Using Encrypted Content Keys with DRM](drm-content-key-encryption.md)\. 

  The following example shows a certificate ARN:

  ```
  arn:aws:acm:region:123456789012:certificate/97b4deb6-8983-4e39-918e-ef1378924e1e
  ```

### Additional Configuration Options for Apple HLS<a name="additional-encryption-parameters"></a>
+ \(Optional\) For **Constant initialization vector** enter a 128\-bit, 16\-byte hex value represented by a 32\-character string, to be used with the key for encrypting content\.

## Static Key Encryption Parameters<a name="static-key-encryption-parameters"></a>

The following options are for static key encryption:
+ **Static key value** – A valid string for encrypting content\.
+ **URL** – The URL to include in the manifest so that content can be decrypted\.