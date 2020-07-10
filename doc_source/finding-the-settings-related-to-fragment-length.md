# Finding the settings related to fragment length<a name="finding-the-settings-related-to-fragment-length"></a>

When you set **Fragment length**, check your values for **Closed GOP cadence**, **GOP size**, and **Framerate**\.

## Fragment length<a name="fragment-length"></a>

You can set the fragment length using either the console or the JSON job specification\. The **Fragment length** setting applies to an output group and affects every output in the group\.

**To find the **Fragment length** setting \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, under **Output groups**, choose the name of your CMAF, DASH ISO, or Microsoft Smooth Streaming output group\.

1. In the group settings section on the right, find **Fragment length**\. 

   The group settings section is titled **CMAF group settings**, **DASH ISO group settings**, or **MS Smooth group settings**\.

**To find the **Fragment length** setting \(JSON job specification\)**
+ Find `FragmentLength` as a child of `OutputGroupSettings`, as in the following example:

  ```
  {
    "Settings": {
      ...
      "Inputs": [
        ...
      ],
      "OutputGroups": [
        {
          "Name": "DASH ISO",
          "OutputGroupSettings": {
            "Type": "DASH_ISO_GROUP_SETTINGS",
            "DashIsoGroupSettings": {
              "SegmentLength": 30,
              "FragmentLength": 2,
              "SegmentControl": "SINGLE_FILE",
              "HbbtvCompliance": "NONE"
            }
          },
  		...
  ```

## Closed GOP cadence, GOP size, and framerate<a name="closed-gop-cadence-gop-size-and-framerate"></a>

You can set **Closed GOP cadence**, **GOP size**, and **Framerate** using either the console or the JSON job specification\. These settings apply to each output individually\. When you set them, make sure that the values you set for each output in the output group work with the value you specify for the output group's **Fragment length**\.

**Note**  
Your ABR stack has multiple outputs\. Make sure to set these values in each output\.

**To find the encoding settings for an output \(console\)**

1. On the **Create job** page, in the **Job** pane on the left, under **Output groups**, choose the name of your output, such as **Output 1**, **Output 2**, and so on\.

1. In the **Encoding settings** section, the **Video** tab is selected automatically\. Find **Closed GOP cadence**, **GOP size**, and **Framerate** on this tab\.

**To find the encoding settings for an output \(JSON job specification\)**
+ 

Find `GopClosedCadence`, `GopSize`, `FramerateNumerator`, and `FramerateDenominator` as children of the codec settings, as in the following example\. In this example, the codec is `H_264`, so the parent of the codec settings is `H264Settings`:

  ```
  {
    "Settings": {
      ...
      "Inputs": [
        ...
      ],
      "OutputGroups": [
        {
          "Name": "DASH ISO",
          ...
          },
          "Outputs": [
            {
              "VideoDescription": {
                ...
                "CodecSettings": {
                  "Codec": "H_264",
                  "H264Settings": {
                    "InterlaceMode": "PROGRESSIVE",
                    "NumberReferenceFrames": 3,
                    "Syntax": "DEFAULT",
                    "Softness": 0,
                    "GopClosedCadence": 1,
                    "GopSize": 60,
  				  ...
                    "FramerateNumerator": 60,
                    "FramerateDenominator": 1
                  }
                },
                ...
              },
  ```