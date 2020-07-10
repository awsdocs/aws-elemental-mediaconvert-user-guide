# Writing your outputs to an Amazon S3 bucket in another account<a name="write-your-outputs-to-another-accounts-amazon-s3-bucket"></a>

When you want the outputs of your MediaConvert jobs to reside in an Amazon S3 bucket that is owned by another AWS account, you work together with the administrator of that account to add a bucket permissions policy that grants you access to write the files and to add an Amazon S3 canned access control list \(ACL\) to the outputs\. Then you set up your MediaConvert job to write to that bucket and to automatically add the canned ACL `bucket-owner-full-control` as it does so\.

The result of this setup is that you own the files, but they reside in another account's bucket\. The owner of the bucket has full access to the files\.

**To write your outputs to a bucket owned by another account**

1. Work with an administrator of the other account to add a bucket policy to the Amazon S3 bucket that you want to write your output files to\. For more information, see [How do I add an S3 Bucket policy?](https://docs.aws.amazon.com/AmazonS3/latest/dev/add-bucket-policy.html) in the *Amazon Simple Storage Service Developer Guide*\.

   The following example bucket policy grants the necessary permissions:

   ```
   {
       "Version": "2012-10-17",
       "Id": "Policy1570060985561",
       "Statement": [
           {
               "Sid": "Stmt1570060984261",
               "Effect": "Allow",
               "Principal": {
                   "AWS": [
                       "arn:aws:iam::111122223333:role/MediaConvertRole"
                   ]
               },
               "Action": [
                   "s3:GetObject",
                   "s3:GetObjectAcl",
                   "s3:ListBucket",
                   "s3:PutObject",
                   "s3:PutObjectAcl"
               ],
               "Resource": [
                   "arn:aws:s3:::bucket",
                   "arn:aws:s3:::bucket/*"
               ]
           }
       ]
   }
   ```

1. For any job that writes outputs to that bucket, apply the **Bucket owner full control** ACL as follows:

   1. Set up your job as usual\. For more information, see [Setting up a job](setting-up-a-job.md)\.

   1. Specify the other account's Amazon S3 bucket for your output **Destination**\. On the **Create job** page, in the **Job** pane on the left, choose an output group\. In the group settings section on the right, find **Destination**\.

   1. Enable **Access control**, and then choose **Bucket owner full control** for **Canned access control list**\.