# Teletext output captions<a name="teletext-output-captions"></a>

How you set up your output Teletext captions depends on whether you want to move the captions to different Teletext pages or to just pass through your captions exactly from the input to the output\.

## Teletext to Teletext passthrough<a name="teletext-to-teletext-passthrough"></a>

When your input captions format is Teletext and you want your output captions to be on the same pages, with the same styling, as the input, then you can pass through the input captions to your output\. To do so, set up your captions this way:
+ Make sure that your input captions are set up with one captions selector\. For more information, see [Teletext input captions](teletext.md)\.
+ In the same output group and same output as your video, create one captions tab\. This one captions tab represents all of your output captions, regardless of the number of output Teletext pages you have\.
+ In your output captions tab, choose your input captions selector for **Captions source**\.
+ Don't specify values for any other settings on the output captions tab\.

When you work directly in your JSON job specification, one captions tab corresponds to one child of `CaptionDescriptions`\.

## Teletext to Teletext, page remapping<a name="teletext-to-teletext-page-remapping"></a>

When your input captions format is Teletext and, in your output, you want to change the Teletext pages that your captions are on, you specify the pages in the input and output\. To do so, set up your captions this way:
+ Make sure that your input captions are set up with one captions selector for each Teletext page and that you specify the page number in the settings for each input captions selector\. For more information, see [Teletext input captions](teletext.md)\.
+ In the same output group and same output as your video, create one captions tab for each output Teletext page\.
+ In each output captions tab, choose one of your input captions selectors for **Captions source**\.
+ In each output captions tab, for **Page number**, specify the Teletext page number that you want for those captions in your output\. Optionally, provide values for **Language**, **Description**, and **Page types**\.

## Teletext from other captions formats<a name="teletext-from-other-captions-formats"></a>

When your input captions are in a format other than Teletext, you must specify the Teletext pages for your output captions\. MediaConvert supports these captions workflows:
+ A single input captions track to a single output Teletext page\.
+ A single input captions track to multiple output Teletext pages\. Each output page duplicates the contents of the others\.
+ Multiple input captions tracks to multiple output Teletext pages\. You use captions selectors to specify which captions to include on each output Teletext page\.

Set up your captions like this:
+ Make sure that your input captions are set up with one captions selector for each captions track that you intend to map to a Teletext page\. For more information, see [Creating input captions selectors](create-input-caption-selectors.md)\.
+ In the same output group and same output as your video, create one captions tab for each output Teletext page\.
+ In each output captions tab, choose one of your input captions selectors for **Captions source**\.
+ In each output captions tab, for **Page number**, specify the Teletext page number that you want for those captions in your output\. Optionally, provide values for **Language** and **Description**\.