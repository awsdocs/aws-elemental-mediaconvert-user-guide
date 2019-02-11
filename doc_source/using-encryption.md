# Using Encryption in AWS Elemental MediaConvert<a name="using-encryption"></a>

Protect your content from unauthorized use through encryption\. Digital rights management \(DRM\) systems provide keys to MediaConvert for content encryption, and licenses to supported players for decryption\.

**Note**  
To encrypt content, you must have a DRM solution provider\.   
For an overview, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/what\-is\-speke\.html\#services\-architecture](https://docs.aws.amazon.com/speke/latest/documentation/what-is-speke.html#services-architecture)\.
To get set up, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/customer\-onboarding\.html](https://docs.aws.amazon.com/speke/latest/documentation/customer-onboarding.html)\.
The only exception to this requirement is with the Apple HLS streaming protocol, where you can choose to either define your own static keys or use a DRM provider\. 

**Topics**
+ [Using Encrypted Content Keys with DRM](drm-content-key-encryption.md)
+ [Encrypting Content](encrypting-content.md)
+ [Troubleshooting Encryption](troubleshooting-encryption.md)