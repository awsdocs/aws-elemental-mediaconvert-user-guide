# Step 5: Upload Files for Transcoding<a name="upload-input-files"></a>

AWS Elemental MediaConvert can take in your input files from Amazon S3 or from a server through HTTP or HTTPS\.<a name="upload-with-s3"></a>

**To upload files to an S3 bucket**

1. In the **Buckets** pane, choose the name of your input bucket\. 

1. Choose **Upload**\.

1. In the **Upload** dialog box, choose **Add files**, and then upload a media file that you want to transcode\.

1. Choose **Upload**\.

## HTTP Input Requirements<a name="http-input-requirements"></a>

When your input file source is HTTP, you specify the URL rather than an Amazon S3 path\. Requirements for using HTTP for input are as follows:
+ The HTTP server must be public\.
+ The HTTP server must not require authentication\.
+ You can use HTTP for your primary video source, but not for sidecar captions, sidecar audio, or graphic overlays\.
+ The URL that you specify must be a direct link to your file; MediaConvert doesn't follow redirects\.
+ The URL that you specify can't be a pre\-signed URL\.