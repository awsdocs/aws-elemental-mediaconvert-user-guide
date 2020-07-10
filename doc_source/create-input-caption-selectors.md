# Creating input captions selectors<a name="create-input-caption-selectors"></a>

When you set up captions, you begin by creating captions selectors\. Captions selectors identify a particular captions asset on the input and associate a label with it\. The captions asset is either a single track or the set of all tracks contained in the input file, depending on your input captions format\. For example, you might add **Captions selector 1** and associate the French captions with it\. When you [set up an output to include captions](set-up-captions-in-outputs.md), you do so by specifying captions selectors\. 

**To create input captions selectors**

1. On the **Create job** page, in the **Job** pane on the left, choose an input\. 
**Note**  
In jobs with multiple inputs, each input must have the same number of captions selectors\. For inputs that don't have captions, create empty captions selectors\. For these selectors, for **Source**, choose **Empty captions track**\.

1. In the **Captions selectors** section, near the bottom of the page, choose **Add captions selector**\. 

1. Under **Source**, choose the input captions format\. 

1. For most formats, more fields appear\. Specify the values for these fields as described in the topic that relates to your input captions format\. Choose the appropriate topic from the list that follows this procedure\.

1. Create more captions selectors as necessary\. The number of captions selectors that you need depends on your input captions format\. Choose the appropriate topic from the list that follows this procedure\.

**Topics**
+ [QuickTime captions track or captions in MXF VANC data \(ancillary\)](ancillary.md)
+ [Embedded \(CEA/EIA\-608, CEA/EIA\-708\), embedded\+SCTE\-20, and SCTE\-20\+embedded](embedded.md)
+ [DVB\-Sub](dvb-sub-or-scte-27.md)
+ [Teletext](teletext.md)
+ [IMSC, SCC, SRT, STL, TTML \(sidecar\)](sidecar-input.md)
+ [IMSC \(as part of an IMF source\)](IMSC-in-MXF.md)