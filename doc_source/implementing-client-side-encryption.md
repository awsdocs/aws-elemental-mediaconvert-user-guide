# Implementing client\-side encryption<a name="implementing-client-side-encryption"></a>

Client\-side encryption is one of the three encryption options that you can use with AWS Elemental MediaConvert\. With client\-side encryption, you encrypt your input files before you upload them to Amazon S3\.

You can use client\-side encryption in conjunction with the other two options\. The following illustration shows the three options\.

![\[Three rectangles represent each of the three encryption options. The first, client-side encryption, is highlighted. The text reads as follows. Client-side encryption: Encrypt your content using open protocols before you upload your input files. Protects your input files in transit. Protects your input files at rest.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/encryption_client-side.png)

When you set up client\-side encryption, you use multiple AWS services, as shown in the following diagram\.

![\[Two rectangles represent your local system and the AWS cloud. In the local system rectangle, icons represent the three steps you do. Text reads: 1. Use AWS Key Management Service (AWS KMS) to generate and encrypt a data encryption key, or generate your data encryption key locally and then encrypt it with AWS KMS. 2. Encrypt your media files. 3. Send your encrypted data key with your job settings to AWS Elemental MediaConvert. In the AWS Cloud rectangle, icons represent AWS KMS, Amazon S3, and MediaConvert. Arrows between the two rectangles show that your local system receives plaintext and encrypted versions of your data key from KMS, that you send your encrypted files to your Amazon S3 input bucket, and that you provide the encrypted version of your data key to MediaConvert in your job settings. Arrows inside the rectangle representing the AWS Cloud show that, because you grant permissions to allow it, MediaConvert can use AWS KMS to decrypt your data key and then use the decrypted data key to decrypt your media files and run your transcoding job.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/client-side-encryption.png)

**To use client\-side encryption with AWS Elemental MediaConvert**

1. Use AWS Key Management Service \(AWS KMS\) to create a customer managed customer master key \(CMK\)\. For procedures, see [Creating keys](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html) in the *AWS Key Management Service Developer Guide*\. For an overview, see [Customer master keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#master_keys) in the same guide\.

1. Create a data key to use to encrypt your content\. Use the AWS KMS [Encrypt](https://docs.aws.amazon.com/kms/latest/APIReference/API_Encrypt.html) operation to encrypt the data key under your customer managed CMK\. You must use this encryption context: 

   ```
   "{\"service\" : \"mediaconvert.amazonaws.com\" }"
   ```

   You can create and encrypt your data key in one the following ways:
   + Create a data key using AWS Key Management Service \(AWS KMS\) by calling KMS [GenerateDataKey](https://docs.aws.amazon.com/kms/latest/APIReference/API_GenerateDataKey.html)\. For the `KeyId` parameter, specify the Amazon Resource Name \(ARN\) of the CMK that you created in the first step of this procedure\. This operation returns a plaintext copy of the data key and a copy that is encrypted under the CMK\.
   + Use an encryption library, such as [OpenSSL](https://www.openssl.org/), to create an [Advanced encryption standard](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) \(AES\) key\. Then, encrypt the key by calling AWS KMS [Encrypt](https://docs.aws.amazon.com/kms/latest/APIReference/API_Encrypt.html)\. Include the CMK that you created in the first step of this procedure as the `KeyId` when you make this call\.

     For more information about creating an AES key using OpenSSL, see the [OpenSSL documentation](https://www.openssl.org/docs/)\.

   For more information, see [data keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#data-keys) in the [AWS Key Management Service concepts](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html) topic of the *AWS Key Management Service Developer Guide*\.

1. Use the plaintext data key that you created in the preceding step to encrypt your content as follows:
   + Use one of the following AES encryption modes: CTR, CBC, or GCM\.
   + Use a 16\-byte initialization vector with any encryption mode\. Or, use a 12\-byte initialization vector with GCM or CTR\.

   For more information about using OpenSSL, see the [OpenSSL documentation](https://www.openssl.org/docs/)\.
**Note**  
AWS Elemental MediaConvert doesn't support files encrypted by using the Amazon S3 encryption client\.

1. Specify AWS Elemental MediaConvert decryption settings for each encrypted input as follows:

   1. On the **Create job** page, in the **Job** pane on the left, choose an **Input**\.

   1. In the **Input** section on the right, choose **Decryption settings**\.

   1. For **Decryption mode**, choose the AES encryption mode that you used to encrypt your content in an earlier step of this procedure\.

   1. For **Encrypted data key**, enter the *encrypted* version of your data key that the AWS KMS `GeneratedDataKey` or `Encrypt` operation returned\.

      Make sure that you provide the encrypted version of your data key\. Providing the data key in plaintext exposes it in transit between your system and MediaConvert, making your content vulnerable\. Also, if you provide your plaintext data key, your job will fail\.

   1. For **Initialization vector**, provide the 16\-byte or 12\-byte initialization vector that you used to encrypt your content in an earlier step of this procedure\.
**Note**  
You must provide your initialization vector encoded in base64\. You can do base64\-encoding with an online conversion tool, or at the Linux command line with the following command: `echo -n "string-to-be-encoded-here" | base64`\. The `-n` flag excludes any newline character from the end of the string that you pass in\.

   1. If the AWS Region that you used for AWS KMS when you generated your data key is different from the Region that you are currently using to run your AWS Elemental MediaConvert job, specify that Region for **AWS Region for decryption key**\.

1. Grant `kms:Decrypt` permissions to your AWS Elemental MediaConvert AWS Identity and Access Management \(IAM\) role\. Use an IAM inline policy\. To learn more, see these topics:
   + For more information about setting up an IAM role for AWS Elemental MediaConvert to assume, see [Step 3: Set up IAM permissions ](iam-role.md) in the Getting Started chapter of this guide\.
   + For more information about granting IAM permissions using an inline policy, see the procedure **To embed an inline policy for a user or role** in [Adding IAM identity permissions \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console) in the *IAM User Guide*\. 
   + For examples of IAM policies that grant AWS KMS permissions, including decrypting encrypted content, see [Customer managed policy examples](https://docs.aws.amazon.com/kms/latest/developerguide/iam-policies.html#customer-managed-policies) in the *AWS Key Management Service Developer Guide*\.