# Including SCTE\-35 Markers in an Output<a name="including-scte-35-markers-in-an-output"></a>

You can include any SCTE\-35 markers from your input in any output that has an MPEG\-2 container\. These outputs might be in an HLS package or they might be standalone files\.

**To pass through SCTE\-35 markers from the input to an output:**

1. Open the MediaConvert console at [https://console\.aws\.amazon\.com/mediaconvert](https://console.aws.amazon.com/mediaconvert)\.

1. Choose **Create new job**\.

1. Set up your input, output groups, and outputs for video and audio, as described in [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md) and [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)\.
**Note**  
SCTE\-35 markers are only present in transport stream inputs, such as MPEG\-2 files\. You can only include them in MPEG\-2 container outputs\. These outputs can be either standalone files or part of an HLS package\.

1. Choose an output under either **File group** or **Apple HLS**\. 

1. Under **Container settings** \(for **File group** outputs\) or **Transport stream settings** \(for **Apple HLS** outputs\), find **SCTE\-35 source** and choose **Passthrough**\.

1. Optionally, under **SCTE\-35 PID**, enter a different value from the default **500**\. 

   A PID, or packet identifier, is an identifier for a set of data in an MPEG\-2 transport stream container\. PIDs are used by downstream systems and players to locate specific information in the container\. 