# Step 4: Upload files for transcoding<a name="upload-input-files"></a>

AWS Elemental MediaConvert can take in your input files from Amazon S3 or from a server through HTTP or HTTPS\. To provide your files from Amazon S3, upload them to your S3 bucket\.<a name="upload-with-s3"></a>

**To upload files to an S3 bucket**

1. In the **Buckets** pane, choose the name of your input bucket\. 

1. Choose **Upload**\.

1. In the **Upload** dialog box, choose **Add files**, and then upload a media file that you want to transcode\.

1. Choose **Upload**\.

**Note**  
For information about supported input files, see [Supported input codecs and containers](reference-codecs-containers-input.md)\. 

## HTTP input requirements<a name="http-input-requirements"></a>

When your input file source is HTTP\(S\), you specify the URL rather than an Amazon S3 path\. Requirements for using HTTP\(S\) for input are as follows:
+ All input files must be publicly readable\.
+ The HTTP\(S\) server must not require authentication\.
+ The HTTP\(S\) server must accept both HEAD and range GET requests\.
+ The URL that you specify can't include parameters\.

If your HTTP\(S\) input uses redirection, it must follow these restrictions:
+ You can redirect only once from the URL that you provide as your input\. You can't redirect to a URL that, in turn, contains a redirect\.
+ The HTTP\(S\) status response code from the initial server must be either 301 or 302\.
+ The HTTP\(S\) response from the initial server must use its `Location` headers to provide the URL that it's redirecting MediaConvert to\.