# Choosing between input overlay and output overlay<a name="choosing-between-input-overlay-and-output-overlay"></a>

You can add still image overlays to your inputs, your outputs, or both\. Where you specify your graphic overlays affects where in your transcoded assets the overlays appear\. 

The following diagram shows how input and output overlays appear in the video files that are created by a job\. Input overlays appear on all outputs, but only in the portions of the outputs that come from the input that has the overlay\. Output overlays appear throughout an entire output, but only on the outputs that have the overlay\.

**Note**  
In this diagram, all overlays are specified for the entire duration of the input or output\. You can instead specify a shorter overlay duration within that time\.

![\[Input and output overlays for a job’s video files, set for the duration of the input or output.\]](http://docs.aws.amazon.com/mediaconvert/latest/ug/images/ImageInserter.png)

## Input overlays<a name="input-overlays"></a>

Choose input overlay for the following situations:
+ You want the same overlays on every output\.
+ You want an overlay on only the parts of your outputs that correspond to individual inputs\.

These examples are situations where you would use input overlay:
+ Some of your inputs already have your logo as an overlay and some of them don't\. You want to add the logo only to the inputs that don't already have it\.
+ Some of your inputs are programming that you want your logo on\. Other inputs are advertisements or blank slates that you don't want your overlay on\.
+ Your job has only one input\. Your overlay should appear for the entire duration of the video and on every output of the job\.

## Output overlays<a name="output-overlays"></a>

Choose output overlay for the following situations:
+ You want overlays on some outputs but not others\.
+ You want different overlays on different outputs\.
+ You have multiple inputs, but you want the same overlay across all of them\.

These examples are situations where you would use output overlay:
+ You set up one of your outputs with high definition\. You want to include an HD indicator in the corner of the frame on this output only\.
+ You are stitching together several films as separate inputs to create a single\-asset film marathon\. You want to put a graphic on all of them indicating that they are part of the larger marathon\.