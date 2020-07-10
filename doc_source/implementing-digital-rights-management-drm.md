# Implementing digital rights management \(DRM\)<a name="implementing-digital-rights-management-drm"></a>

DRM is one of the three encryption options that you can use with AWS Elemental MediaConvert\. You can use it in conjunction with the other two options\. The following illustration shows the three options\.

![\[Three rectangles represent each of the three encryption options. The third, DRM, is highlighted. The text reads as follows. Use digital rights management (DRM) to protect your content during distribution. Protects your output files in transit. Protects your output files at rest.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/encryption_DRM.png)

Protect your content from unauthorized use through encryption\. Digital rights management \(DRM\) systems provide keys to AWS Elemental MediaConvert for content encryption, and licenses to supported players and other consumers for decryption\.

**Note**  
To encrypt content, you must have a DRM solution provider\.   
For an overview, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/what\-is\-speke\.html\#services\-architecture](https://docs.aws.amazon.com/speke/latest/documentation/what-is-speke.html#services-architecture)\.
To get set up, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/customer\-onboarding\.html](https://docs.aws.amazon.com/speke/latest/documentation/customer-onboarding.html)\.
The only exception to this requirement is with the Apple HLS streaming protocol, where you can choose to either define your own static keys or use a DRM provider\. 

**Topics**
+ [Encrypting content](encrypting-content.md)
+ [Using encrypted content keys with DRM](drm-content-key-encryption.md)
+ [Troubleshooting DRM encryption](troubleshooting-encryption.md)