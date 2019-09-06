# Example ESAM XML Signal Processing Notification<a name="example-esam-xml"></a>

This ESAM XML block generates two 30\-second ad breaks, one at 10 seconds in and the other at 75 seconds in\. The second spot is divided into two 15\-second breaks\.

```
<![CDATA[<SignalProcessingNotification xmlns="urn:cablelabs:iptvservices:esam:xsd:signal:1" xmlns:sig="urn:cablelabs:md:xsd:signaling:3.0" xmlns:common="urn:cablelabs:iptvservices:esam:xsd:common:1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" acquisitionPointIdentity="ExampleESAM">
    <common:BatchInfo batchId="1">
      <common:Source xsi:type="content:MovieType" uriId="/mnt/support/bferrentino/teting_content/HEVC_rap"/>
    </common:BatchInfo>
    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="1" signalPointID="10.00" action="create">
      <sig:NPTPoint nptPoint="10.00"/>
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="1" segmentTypeId="52" upidType="9" upid="1" duration="30.00" segmentNumber="1" segmentsExpected="1"/>
      </sig:SCTE35PointDescriptor>
      <sig:StreamTimes>
        <sig:StreamTime timeType="HLS"/>
      </sig:StreamTimes>
    </ResponseSignal>
    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="2" signalPointID="40.00" action="create" segmentNumber="1" segmentsExpected="0">
      <sig:NPTPoint nptPoint="40.00" />
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="1" segmentTypeId="53" upidType="9" upid="2"/>
      </sig:SCTE35PointDescriptor>
      <sig:StreamTimes>
        <sig:StreamTime timeType="HLS"/>
      </sig:StreamTimes>
    </ResponseSignal>
    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="3" signalPointID="75.00" action="create">
      <sig:NPTPoint nptPoint="75.00"/>
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="2" segmentTypeId="52" upidType="9" upid="3" duration="30.00" segmentNumber="2" segmentsExpected="2"/>
      </sig:SCTE35PointDescriptor>
      <sig:StreamTimes>
        <sig:StreamTime timeType="HLS"/>
      </sig:StreamTimes>
    </ResponseSignal>
    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="4" signalPointID="105.00" action="create" segmentNumber="1" segmentsExpected="0">
      <sig:NPTPoint nptPoint="105.00" />
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="2" segmentTypeId="53" upidType="9" upid="4"/>
      </sig:SCTE35PointDescriptor>
      <sig:StreamTimes>
        <sig:StreamTime timeType="HLS"/>
      </sig:StreamTimes>
    </ResponseSignal>
    <ConditioningInfo acquisitionSignalIDRef="1" startOffset="PT10S" duration="PT30S"/>
    <ConditioningInfo acquisitionSignalIDRef="3" startOffset="PT75S" duration="PT30S">
      <Segment>PT15S</Segment>
      <Segment>PT15S</Segment>
    </ConditioningInfo>
  </SignalProcessingNotification>
  ]]>
```