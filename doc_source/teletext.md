# Teletext input captions<a name="teletext"></a>

How you set up your Teletext input captions selectors depends on how you plan to use the captions in your output\. You can use Teletext captions in one of the following ways:
+ [Teletext to Teletext passthrough](#input-teletext-to-output-teletext-passthrough)

  With Teletext passthrough, MediaConvert passes through your input captions unchanged from the input to the output\. Captions styling, Teletext page numbers, and non\-caption Teletext data appear in your outputs exactly the same as in the input\.

  Teletext passthrough is the only way to include Teletext data that isn't captions in your output\.
+ [Teletext to Teletext, page remapping](#input-teletext-to-output-teletext-with-page-remapping)

  If you want the Teletext page numbers on your output to differ from the page numbers on the input, you can remap the content\. When you do this, your output captions have plain styling and you lose any Teletext data that isn't captions\.
+ [Teletext to other captions formats](#input-teletext-to-other-format-output-captions)

  You can use Teletext input captions to generate output captions in some other formats\. To look up which captions you can generate from Teletext inputs, see [Captions supported by AWS Elemental MediaConvert](captions-support-tables.md)\.

For information on setting up captions for each of these workflows, see the following topics\.

## Teletext to Teletext passthrough<a name="input-teletext-to-output-teletext-passthrough"></a>

When you're doing Teletext to Teletext passthrough, create one input captions selector for the whole set of input captions\. Don't specify a value for **Page number**\.

For information about setting up the output of this captions workflow, see [Teletext to Teletext passthrough](teletext-output-captions.md#teletext-to-teletext-passthrough)\.

## Teletext to Teletext, page remapping<a name="input-teletext-to-output-teletext-with-page-remapping"></a>

When the captions format for both your input and output captions is Teletext, and you want your output Teletext page numbers to be different from the input page numbers, create a separate input captions selector for each Teletext page of your input\. Specify the input Teletext page number for **Page number**\.

For information about setting up the output of this captions workflow, see [Teletext to Teletext, page remapping](teletext-output-captions.md#teletext-to-teletext-page-remapping)\.

## Teletext to other captions formats<a name="input-teletext-to-other-format-output-captions"></a>

When your input captions are Teletext and your output captions are another format, set up one input captions selector for each input Teletext page\. Specify the input Teletext page number for **Page number**\.

For information about setting up the output of this captions workflow, see the section on your output format in [Setting up captions in outputs](set-up-captions-in-outputs.md)\.