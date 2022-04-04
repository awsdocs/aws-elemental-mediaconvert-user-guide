# TTML style formatting<a name="ttml-style-formatting"></a>

AWS Elemental MediaConvert reads the style formatting of your input captions when your job runs\. If you notice issues with the style formatting of your output, we recommend checking the formatting of your input captions\. The following topics provide guidance for using fonts, heritable and non\-heritable attributes, and right to left languages in your TTML input captions\.

**Specifying fonts** 

MediaConvert supports the following generic font families listed in the [TTML2 W3C recommendation](https://www.w3.org/TR/ttml2/#style-value-generic-family-name): 
+ default
+ monospace
+ sansSerif
+ serif
+ monospaceSansSerif
+ monospaceSerif
+ proportionalSansSerif
+ proportionalSerif

For the best results, specify a generic font family within your TTML input captions\. If you specify an individual font instead, MediaConvert will map the font to one of the generic font families listed above\.

**Heritable and non\-heritable attributes** 

Style attributes are either heritable or non\-heritable\. The [TTML 2 W3C recommendation](https://www.w3.org/TR/ttml2/#styling-attribute-vocabulary) lists these under *inherited* for each style attribute\.

Include non\-heritable style attributes in every element that you want them to apply to\.

For example, `tts:backgroundColor` is a non\-heritable style attribute\. The following results in *hello* with a red background color and *world* with no background color: 

`<span tts:backgroundColor="red">hello<br/>world</span>` 

You can fix the above formatting so that *hello world* both have a red background color by using individual spans, each with their own style attributes, like in this example: 

`<span><span tts:backgroundColor="red">hello</span> <br/> <span tts:backgroundColor="red">world</span></span>` 

**Right to left languages** 

MediaConvert supports both left to right and right to left text directions within TTML\. 

When you don’t specify text direction, MediaConvert uses left to right\. 

To specify right to left, include a `tts:direction="rtl"` attribute\. If your text has a mix of bidirectional characters, also include a `tts:unicodeBidi="embed"` attribute as described in the [TTML2 W3C recommendation](https://www.w3.org/TR/ttml2/#style-attribute-direction)\. Note that `tts:unicodeBidi` is a non\-heritable attribute\.