# About sizing your overlay to account for scaling<a name="about-overlay-scaling"></a>

In jobs that scale the video resolution, whether your overlay scales with your video depends on where you specify the graphic overlay\. Motion graphic overlay and input overlays scale with the video; output overlays don't\.

For example, suppose that the input video for your job is 1080 x 1920 and you specify three outputs at 720 x 1280, 480 x 640, and 360 x 480\. You want your square logo to be 10% of the width of your frames\. You would provide overlay images at the following resolutions:
+ For a motion graphic overlay or an input graphic overlay, provide an image that is 108 x 108\. The service appropriately sizes each overlay on each output\.
+ For an output graphic overlay on your 720 x 1280 output, provide an image that is 72 x 72\.
+ For an output graphic overlay on your 480 x 640 output, provide an image that is 48 x 48\.
+ For an output graphic overlay on your 360 x 480 output, provide an image that is 36 x 36\.