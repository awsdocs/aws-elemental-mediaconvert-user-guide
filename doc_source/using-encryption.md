# Data protection for AWS Elemental MediaConvert<a name="using-encryption"></a>

Use encryption to protect your content from unauthorized access\. You can use any combination of these encryption options with AWS Elemental MediaConvert:
+ Client\-side encryption: Encrypt your input files before you upload them to Amazon S3 to protect them in transit\.
+ Server\-side encryption: Keep your output files secure in the Amazon S3 buckets that AWS Elemental MediaConvert reads from and writes to\.
+ Digital rights management \(DRM\): Make sure that, once you distribute your content, only authorized viewers can watch it\.

The following illustration shows these encryption options\.

![\[Three rectangles represent each of the three encryption options. The text reads as follows. 1. Client-side encryption: Encrypt your content using open protocols before you upload your input files. Protects your input files in transit. Protects your input files at rest. 2. Server-side encryption: Use Amazon S3 default bucket encryption to encrypt your files as they enter the S3 buckets. You can use this as you upload your input files and as MediaConvert writes your output files. Protects your files at rest. 3. DRM: Use digital rights management (DRM) to protect your content during distribution. Protects your output files in transit. Protects your output files at rest.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/encryption_overview.png)

**Topics**
+ [Implementing client\-side encryption](implementing-client-side-encryption.md)
+ [Implementing server\-side encryption](implementing-server-side-encryption.md)
+ [Implementing digital rights management \(DRM\)](implementing-digital-rights-management-drm.md)