# Creating additional manifests<a name="create-additional-manifests"></a>

By default, MediaConvert generates a single top\-level manifest for each of your CMAF, DASH ISO, Apple HLS, and Microsoft Smooth Streaming output groups\. This default manifest references all the outputs in the output group\. Optionally, you can create additional top\-level manifests that reference only a subset of the outputs in your output group\. For example, you might want to create a manifest that doesn't include HDR outputs, for viewers who don't have a subscription that includes HDR\.

**Note**  
For CMAF output groups, if you keep the default enabled value for **Write HLS manifest** and **Write DASH manifest**, MediaConvert creates additional manifests in both of those formats\. If you disable either of those settings, MediaConvert doesn't create additional manifests in that format\.

**To create an additional manifest**

1. On the **Create job** page, in the **Job** pane on the left, choose the output group that you want to create the additional manifest for\.

1. In the **Additional manifests** section on the right, choose **Add manifest**\.

1. For **Manifest name modifier**, enter the text that you want added to the end of the manifest file name, before the extension\. This setting is required, because it ensures that each manifest has a different file name\.

1. For **Select outputs**, choose the outputs that you want the manifest to refer to\.

1. Repeat these steps to create up to 10 additional manifests\. Each additional manifest must have a different value for **Manifest name modifier**\.