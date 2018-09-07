# DVB\-Sub<a name="dvb-sub-or-scte-27"></a>

MediaConvert supports DVB\-Sub  only in TS inputs\.

In most cases, create one captions selector per language\. In each selector, specify which language you want by providing the PID or language code\.

**Note**  
Don't specify the captions in both the **PID** field and the **Language** dropdown list\. Specify one or the other\. 

If you are doing DVB\-sub\-to\-DVB\-sub and you want to pass through all the captions languages from the input to the output, create one captions selector for all languages\. In this case, keep the **PID **field blank and don't choose any language from the **Language** dropdown list\.