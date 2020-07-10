# Step 4: Create outputs<a name="create-outputs"></a>

After you create output groups, set up your outputs in each group\. How many outputs go in each output group depends on the output group type, as follows:
+ For **File** output groups, include all elements of the media asset in one output\. This includes any audio or captions that you provide in a separate file\. 
+ For ABR streaming output groups—**CMAF**, **Apple HLS**, **DASH ISO**, and **Microsoft Smooth Streaming**—create a separate output for each media element\. That is, one output per video resolution, one output per audio track, and one output per captions language\.

From the following list, choose the procedures that correspond to the output group types that you created in [Step 3: Create output groups](specify-output-groups.md)\.

**Topics**
+ [Creating outputs in ABR streaming output groups](create-outputs-in-abr-streaming-output-groups.md)