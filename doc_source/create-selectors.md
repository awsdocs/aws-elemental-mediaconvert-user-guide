# Step 2: Create input selectors for video, audio, and captions<a name="create-selectors"></a>

Next, create input selectors to flag the video, audio, and captions elements from your input that you will use in your outputs\. This labels each input element so that you can point to it when you set up your outputs\. When you set up input selectors, you also provide the service with information about where to find the data and how to interpret it\. The following illustration shows the three types of input selectors\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/Job_input-selectors.png)

**To set up your input selectors**

1. In the **Video selector** section, specify values for the fields that are applicable to your job\. 

   You don't need to create a video selector because AWS Elemental MediaConvert automatically creates a video selector when you begin setting up a job\. However, the service doesn't automatically detect information about the video source\. You can provide this information in the **Video selector** fields\. If you leave these settings in their default state, you will create a valid job\. For more information about individual settings, choose the **Info** link next to each setting\.
**Note**  
 AWS Elemental MediaConvert doesn't support inputs with multiple video streams, such as Quad 4k\. Each input can have only one video selector; therefore, there is no **Add video selector** button on the console\.

1. In the **Audio selectors** section, under **Audio selector 1**, specify information about your primary audio asset\. You don't need to create an audio selector 1 because the service automatically creates the first audio selector when you begin setting up a job\.
**Note**  
An *audio asset* is often dialogue, background sound, and music together in one track\. Tracks often consist of multiple channels\. For example, Dolby 5\.1 sound has six channels per track\.

   1. For **Selector type**, choose the way that your audio assets are identified\. Often, this is by track\.

   1. Provide the identifier \(that is, track number, PID, or language code\) for your primary audio asset\. Your primary audio asset is likely to be track 1\.
**Note**  
For most use cases, you associate one input track per input selector\. If your use case requires combining multiple tracks into one track, or multiple tracks into one rendition of a streaming package, combine multiple input tracks in one audio selector by typing a comma\-separated list\. For more information about combining tracks, see [More about audio tracks and audio selectors](more-about-audio-tracks-selectors.md)\.

   1. If your audio is in a separate file from your video, choose the **External file** slider switch element and provide the URI to your audio input file that is stored in Amazon S3 or on an HTTP\(S\) server\. For Amazon S3 inputs, you can specify the URI directly or choose **Browse** to select from your Amazon S3 buckets\. For HTTP\(S\) inputs, provide the URL to your input video file\. For more information, see [HTTP input requirements](upload-input-files.md#http-input-requirements)\. 

1. If you have additional audio assets—for example, multiple language tracks—choose **Add audio selector** and provide information about the next asset as described in the preceding step of this procedure\.

1. In the **Captions selectors** section, choose **Add captions selector** to create input captions selectors for any sets of captions that you plan to use in an output\. For more information about setting up captions for your job, see [Setting up captions in MediaConvert jobs](including-captions.md)\.