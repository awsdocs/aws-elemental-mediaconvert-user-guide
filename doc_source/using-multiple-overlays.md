# About specifying the overlay **Layer**<a name="using-multiple-overlays"></a>

The **Layer** setting specifies how overlapping graphic overlays appear in the video\. The service overlays graphics with higher values for **Layer** on top of overlays with lower values for **Layer**\. Each overlay must have a unique value for **Layer**; you can't assign the same layer number to more than one overlay\.

The following illustration shows how the value for **Layer** affects how a graphic overlay appears in relation to other overlays\. The triangle has the highest value for **Layer** and appears on top, obscuring the video frame and all graphic overlays with lower values of **Layer**\.

![\[The underlying video is obscured by three graphic overlays: a blue rectangle with a Layer value of 1, a green ring with a Layer value of 2, and an orange triangle with a Layer value of 3. Where the rectangle and ring overlap, the ring obscures the rectangle. Where the triangle and ring overlap, the triangle obscures the ring. In the transparent portion of the ring, the underlying video and a corner of the rectangle show through.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/ImgIns-Layer.png)

**To specify a value for the **Layer** setting**

1. Set up your graphic overlay as described in [Still graphic overlay](setting-up-a-graphic-overlay.md)\.

1. For **Layer**, enter a whole number from 0 to 99\. 
**Note**  
You can use each number only once\. Each graphic overlay must have its own layer\.