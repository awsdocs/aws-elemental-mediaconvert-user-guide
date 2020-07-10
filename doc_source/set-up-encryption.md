# Step 4: \(Optional\) Get set up to use DRM encryption<a name="set-up-encryption"></a>

Protect your content from unauthorized use through encryption\. Digital rights management \(DRM\) systems provide keys to AWS Elemental MediaConvert for content encryption, and licenses to supported players and other consumers for decryption\.

To encrypt content, you must have a DRM solution provider\. 
+ For an overview, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/what\-is\-speke\.html\#services\-architecture](https://docs.aws.amazon.com/speke/latest/documentation/what-is-speke.html#services-architecture)\.
+ To get set up, see [https://docs\.aws\.amazon\.com/speke/latest/documentation/customer\-onboarding\.html](https://docs.aws.amazon.com/speke/latest/documentation/customer-onboarding.html)\.

The only exception to this requirement is with the Apple HLS streaming protocol, where you can choose to define your own static keys or to use a DRM provider\. 