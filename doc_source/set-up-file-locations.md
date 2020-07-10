# Step 2: Create storage for files<a name="set-up-file-locations"></a>

AWS Elemental MediaConvert transcodes your input files to generate output files\. MediaConvert can take in your input files from Amazon S3 or from a server through HTTP or HTTPS\. For your output locations, MediaConvert works with Amazon S3 buckets\.<a name="create-s3-buckets-procedure"></a>

**To create an Amazon S3 bucket**

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console\.aws\.amazon\.com/s3/](https://console.aws.amazon.com/s3/)\.

1. On the Amazon S3 console, choose **Create bucket**\.

1. In the **Create bucket** dialog box, type a bucket name\. If you want to create separate input and output buckets, give the bucket an appropriate name that will help you identify it later\.

1. Choose a Region for your bucket\. Make sure that you create your Amazon S3 buckets and do your MediaConvert transcoding in the same Region\.

1. Choose **Create**\.

1. If you want to create separate buckets for your input files and output files, repeat steps 2 through step 5\. 