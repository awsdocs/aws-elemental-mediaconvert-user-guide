# Converting dual SCC input files to embedded captions<a name="converting-dual-scc-input-files-to-embedded-captions"></a>

If you want to use two SCC files as your captions input and embed the captions as two output captions channels embedded in your output video stream, set up your captions according to this procedure\.

**To convert dual SCC to embedded captions**

1. Set up two input captions selectors\. Follow the procedure in [Creating input captions selectors](create-input-caption-selectors.md)\. Specify values as follows:
   + In each captions selector, choose **SCC** for **Source**\.
   + For **Source file**, choose one of your input SCC files in each selector\.
   + If you want both 608 and 708 captions embedded in your outputs, choose **Upconvert** for **Force 608 to 708 upconvert** in both captions selectors\.

1. Set up captions in your outputs\. Follow the procedure in [Setting up captions in outputs](set-up-captions-in-outputs.md)\. Follow these specific choices:
   + Specify the captions in the same output as the video that you want the captions embedded in\.
   + Choose **Add captions** twice, to create **Captions 1** and **Captions 2** tabs in the **Encoding settings** section\.
   + For **Captions source**, in each of the captions tabs, choose one of the captions selectors that you created in the preceding step of this procedure\.
   + For **CC channel number**, choose a number for each of the captions tabs that don't share a field\. For example, in **Captions 1**, choose **1** for **CC channel number** and in **Captions 2**, choose **3** for **CC channel number**\.

     Don't choose the combinations 1 and 2 or 3 and 4, because those pairs of channels share the same field\.
   + If you chose **Upconvert** in the preceding step of this procedure, optionally specify a service number for **708 service number**\. Within an output, each captions tab must specify a different service number\.

     If you upconvert and don't specify a value for **708 service number**, the service uses the value that you specify for **CC channel number** as your 708 service number\.