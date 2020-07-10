# Example ESAM XML signal processing notification<a name="example-esam-xml"></a>

This ESAM XML block generates two 30\-second ad breaks, one at 10 seconds in and the other at 75 seconds in\.

```
<?xml version="1.0" encoding="UTF-8"?>
<SignalProcessingNotification xmlns="urn:cablelabs:iptvservices:esam:xsd:signal:1" xmlns:sig="urn:cablelabs:md:xsd:signaling:3.0" xmlns:common="urn:cablelabs:iptvservices:esam:xsd:common:1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" acquisitionPointIdentity="ExampleESAM">

    <common:BatchInfo batchId="1">
      <common:Source xsi:type="content:MovieType" />
    </common:BatchInfo>

    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="1" signalPointID="10.00" action="create">
      <sig:NPTPoint nptPoint="10.00"/>
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="1" segmentTypeId="52" upidType="9" upid="1" duration="PT30S" segmentNumber="1" segmentsExpected="1"/>
      </sig:SCTE35PointDescriptor>
    </ResponseSignal>
    <ConditioningInfo acquisitionSignalIDRef="1" startOffset="PT10S" duration="PT30S"/>

    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="2" signalPointID="40.00" action="create">
      <sig:NPTPoint nptPoint="40.00" />
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="1" segmentTypeId="53" upidType="9" upid="2"/>
      </sig:SCTE35PointDescriptor>
    </ResponseSignal>

    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="3" signalPointID="75.00" action="create">
      <sig:NPTPoint nptPoint="75.00"/>
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="2" segmentTypeId="52" upidType="9" upid="3" duration="PT30S" segmentNumber="2" segmentsExpected="1"/>
      </sig:SCTE35PointDescriptor>
    </ResponseSignal>
    <ConditioningInfo acquisitionSignalIDRef="3" startOffset="PT75S" duration="PT30S"/>
    
    <ResponseSignal acquisitionPointIdentity="ExampleESAM" acquisitionSignalID="4" signalPointID="105.00" action="create">
      <sig:NPTPoint nptPoint="105.00" />
      <sig:SCTE35PointDescriptor spliceCommandType="06">
        <sig:SegmentationDescriptorInfo segmentEventId="2" segmentTypeId="53" upidType="9" upid="4"/>
      </sig:SCTE35PointDescriptor>
    </ResponseSignal>

</SignalProcessingNotification>
```