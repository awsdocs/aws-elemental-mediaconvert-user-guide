# Passing through SCTE\-35 markers from your input<a name="passing-through-scte-35-markers"></a>

You can include time\_signal SCTE\-35 markers from your input in any output that has a transport stream container\. These outputs might be in an HLS package, or they might be standalone files wrapped in an MPEG2 transport stream \(M2TS\) container\.

**To pass through SCTE\-35 markers from the input to an output \(console\)**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create job**\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting up a job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring complex jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.

1. Choose an output under either **File group**, **DASH ISO**, or **Apple HLS**\. 

1. Under **Container settings** \(for **File group** outputs\), **Container settings** \(for **DASH ISO** outputs\), or **Transport stream settings** \(for **Apple HLS** outputs\), find **SCTE\-35 source**, and then choose **Passthrough**\.

1. Optional\. For outputs in a **File group** output group, when you set **Output settings**, **Container** to **MPEG\-2 Transport Stream** \(M2TS\), you can enter a value for **SCTE\-35 PID** that is different from the default **500**\. 

   A PID, or packet identifier, is an identifier for a set of data in an MPEG\-2 transport stream container\. PIDs are used by downstream systems and players to locate specific information in the container\. 

1. Optional\. For outputs in an **Apple HLS** output group, you can set up the job to include ad markers in the manifest\. For more information, see [Including SCTE\-35 information in your HLS manifest](including-scte-35-information-in-your-hls-manifest.md)\.