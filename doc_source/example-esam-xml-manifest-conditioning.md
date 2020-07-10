# Example ESAM XML Manifest Confirm Condition Notification<a name="example-esam-xml-manifest-conditioning"></a>

This ESAM manifest confirm condition \(MCC\) XML document generates HLS manifest cue tags for two 30\-second ad breaks\. The first begins at 10 seconds in; the second begins at 75 seconds in\. These cue manifest tags also contain data that can be used by a downstream client for ad replacement and insertion\. Outputs generated with this MCC document contain a SCTE\-35 message embedded into the transport stream file at the first ad break, but not at the second one\.

Note the `dataPassThrough` attribute on the first ad break\. When this attribute is present and set to `"true"`, MediaConvert inserts SCTE\-35 markers in the transport stream as well as in the manifest\. For any ad break that you want marked only in the manifest, leave out the `dataPassThrough` attribute\.

MediaConvert supports manifest conditioning with ESAM only in HLS packages\.

```
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<ns2:ManifestConfirmConditionNotification xmlns:ns2="http://www.cablelabs.com/namespaces/metadata/xsd/confirmation/2" xmlns="http://www.cablelabs.com/namespaces/metadata/xsd/core/2" xmlns:ns3="http://www.cablelabs.com/namespaces/metadata/xsd/signaling/2">
  <ns2:ManifestResponse acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="1" duration="PT30S" dataPassThrough="true"> 
  <ns2:SegmentModify>
      <ns2:FirstSegment>
        <ns2:Tag value="#EXT-X-CUE-OUT:4,SpliceType=VOD_DAI,Action=REPLACE, PAID=amazon.com/TEST2014020500000346,Acds=BA" />
      </ns2:FirstSegment>
      <ns2:SpanSegment>
        <ns2:Tag value="#EXT-X-CUE-OUT-CONT:${secondsFromSignal}/4, SpliceType=VOD_DAI,Action=REPLACE,PAID=amazon.com/TEST2014020500000346,Acds=BA" adapt="true" />
      </ns2:SpanSegment>
      <ns2:LastSegment>
        <ns2:Tag value="#EXT-X-CUE-IN:4,SpliceType=VOD_DAI" locality="after" adapt="true" />
      </ns2:LastSegment>
    </ns2:SegmentModify>
	</ns2:ManifestResponse>
  <ns2:ManifestResponse acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="2"></ns2:ManifestResponse>
  <ns2:ManifestResponse acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="3" duration="PT30S">  
  <ns2:SegmentModify>
      <ns2:FirstSegment>
        <ns2:Tag value="#EXT-X-OUT:4,SpliceType=VOD_DAI,Action=REPLACE, PAID=amazon.com/TEST2014020500000347,Acds=BA" />
      </ns2:FirstSegment>
      <ns2:SpanSegment>
        <ns2:Tag value="#EXT-X-OUT-CONT:${secondsFromSignal}/4, SpliceType=VOD_DAI,Action=REPLACE,PAID=amazon.com/TEST2014020500000346,Acds=BA" adapt="true" />
      </ns2:SpanSegment>
      <ns2:LastSegment>
        <ns2:Tag value="#EXT-X-CUE-IN:4,SpliceType=VOD_DAI" locality="after" adapt="true" />
      </ns2:LastSegment>
    </ns2:SegmentModify>
	</ns2:ManifestResponse>
	<ns2:ManifestResponse acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="4"></ns2:ManifestResponse>
</ns2:ManifestConfirmConditionNotification>
```