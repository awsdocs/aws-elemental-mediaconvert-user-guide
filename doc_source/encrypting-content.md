# Encrypting content<a name="encrypting-content"></a>

Use the following procedure to enable content encryption in **CMAF**, **DASH ISO**, **Apple HLS**, and **MS Smooth** output groups\.

 To use this procedure, you should be comfortable working with output groups\. For more information, see [Step 3: Create output groups](specify-output-groups.md)\.

**To encrypt content**

1. Set up your transcoding job as usual\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. On the **Create job** page, in the **Job** pane on the left, under **Output groups**, choose an output group that you want to enable encryption for\.

1. Turn on **DRM encryption**\.

1. For **CMAF** and **Apple HLS** output groups, choose the encryption method\. Make sure that you choose an encryption method that works with the DRM system that you use\.

   For **DASH ISO** and **MS Smooth** output groups, you don't specify the encryption method\. MediaConvert always uses AES\-CTR \(AES\-128\) encryption with these output groups\.

1. For **CMAF** and **Apple HLS** output groups, choose the source for the content encryption key\. For **Key provider type**, choose **SPEKE** to encrypt using a key provided by your DRM solution provider, or choose **Static key** to enter your own key\.

   For **DASH ISO** and **MS Smooth** output groups, you don't specify the source for the content encryption key\. With these output groups, MediaConvert does DRM only with a SPEKE\-compliant key provider\.
   + For **SPEKE**, fill in the encryption parameter fields\. For more information, see [SPEKE encryption parameters](#speke-encryption-parameters)\. 
   + For **Static Key**, see [Static key encryption parameters](#static-key-encryption-parameters)\.

## SPEKE encryption parameters<a name="speke-encryption-parameters"></a>

When you request encryption, you provide input parameters that allow the service to locate your DRM solution provider's key server, to authenticate you as a user and to request the proper encoding keys\. Some options are available only for particular output groups\.

Enter the SPEKE encryption parameters as follows: 
+ For **Resource ID**, enter an identifier for the content\. The service sends this to the key server to identify the current endpoint\. How unique you make this depends on how fine\-grained you want access controls to be\. The service does not allow you to use the same ID for two simultaneous encryption processes\. The resource ID is also known as the content ID\. 

  The following example shows a resource ID\.

  ```
  MovieNight20171126093045
  ```
+  For **System ID**, enter unique identifiers for your streaming protocol and DRM system\. The number of system IDs that you can specify varies depending on the output group type:
  + CMAF – For **System IDs signaled in DASH**, specify at least one and up to three IDs\. For **System ID signaled in HLS**, specify one ID\.
  + DASH – For **System ID**, specify at least one and up to two IDs\.
  + Apple HLS – For **System ID**, specify one ID\.

  If you provide more than one system ID in a single field, enter them on separate lines, and don't separate them with commas or any other punctuation\. 

  For a list of common system IDs, see [DASH\-IF System IDs](https://dashif.org/identifiers/content_protection/)\. If you don't know your IDs, ask your DRM solution provider\.
+ For **URL**, enter the URL of the API Gateway proxy that you set up to talk to your key server\. The API Gateway proxy must reside in the same AWS Region as MediaConvert\.

  The following example shows a URL\. 

  ```
  https://1wm2dx1f33.execute-api.us-west-2.amazonaws.com/SpekeSample/copyProtection
  ```
+ \(Optional\) For **Certificate ARN**, enter a 2048 RSA certificate ARN to use for content key encryption\. Use this option only if your DRM key provider supports content key encryption\. If you use this and your key provider doesn't support it, the request fails\.

  To enter a certificate ARN here, you must have already imported the corresponding certificate into AWS Certificate Manager, entered the certificate ARN from ACM into the MediaConvert **Certificates** pane, and associated it with MediaConvert\. For more information, see [Using encrypted content keys with DRM](drm-content-key-encryption.md)\. 

  The following example shows a certificate ARN\.

  ```
  arn:aws:acm:region:123456789012:certificate/97b4deb6-8983-4e39-918e-ef1378924e1e
  ```

### Additional configuration options for Apple HLS and CMAF<a name="additional-encryption-parameters"></a>
+ \(Optional\) For **Constant initialization vector** enter a 128\-bit, 16\-byte hex value represented by a 32\-character string, to be used with the key for encrypting content\.

## Static key encryption parameters<a name="static-key-encryption-parameters"></a>

The following options are for static key encryption:
+ **Static key value** – A valid string for encrypting content\.
+ **URL** – The URL to include in the manifest so that player devices can decrypt the content\.