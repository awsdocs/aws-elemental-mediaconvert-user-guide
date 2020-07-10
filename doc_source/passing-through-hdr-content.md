# Passing through HDR content<a name="passing-through-hdr-content"></a>

By default, AWS Elemental MediaConvert sets your color space to **Follow**, which means that your output color space is the same as your input color space, even if the color space changes over the course of the video\. Also by default, MediaConvert sets the output setting **Color metadata** to **Insert**, so that any color metadata is included in the output\. If you want your output HDR to be the same as your input video, keep this setting and make sure that you choose HEVC for your codec and a 10\-bit profile\.

**To pass through HDR content**

1. Set up your transcoding job as usual\. For more information, see [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md)\.

1. Make sure that the input **Color space** is set to the default value **Follow**\.

   1. On the **Create job** page, in the **Job** pane on the left, choose **Input 1**\.

   1. In the **Video selector** section on the right, for **Color space**, choose **Follow**\.

1. For each HDR output, choose an appropriate codec and profile and make sure that **Color metadata** is set to the default value **Insert**\.

   1. On the **Create job** page, in the **Job** pane on the left, choose the output, such as **Output 1**\.

   1. In the **Encoding settings** section on the right, specify these video settings as follows:
**Tip**  
The simplest way to find specific encoding settings in the console is to use your web browser’s search on page function\. For many browsers, this search is case sensitive\.
      + **Video codec** – Choose **HEVC \(H\.265\)**\.
      + **Profile** – Choose one of the 10\-bit profiles: **Main10/Main**, **Main10/High**, **Main 4:2:2 10\-bit/Main**, or **Main 4:2:2 10\-bit/High**\.
      + **Color metadata** – Choose **Insert**\.