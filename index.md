# AWS Elemental MediaConvert User Guide

-----
*****Copyright &copy; 2018 Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in 
     connection with any product or service that is not Amazon's, 
     in any manner that is likely to cause confusion among customers, 
     or in any manner that disparages or discredits Amazon. All other 
     trademarks not owned by Amazon are the property of their respective
     owners, who may or may not be affiliated with, connected to, or 
     sponsored by Amazon.

-----
## Contents
+ [What Is AWS Elemental MediaConvert?](what-is.md)
+ [Getting Started with AWS Elemental MediaConvert](getting-started.md)
   + [Step 1: Sign Up for AWS](gs-1-sign-up.md)
   + [Step 2: Create Storage for Files](set-up-file-locations.md)
   + [Step 3: Set Up IAM Permissions](iam-role.md)
   + [Step 4: (Optional) Get Set Up to Use Encryption](set-up-encryption.md)
   + [Step 5: Upload Files for Transcoding](upload-input-files.md)
   + [Step 6: Create a Job](create-a-job.md)
+ [Setting Up a Job in AWS Elemental MediaConvert](setting-up-a-job.md)
+ [Structuring Complex Jobs in AWS Elemental MediaConvert](structuring-complex-jobs.md)
   + [How Output Groups Affect Outputs in AWS Elemental MediaConvert](outputs-file-ABR.md)
   + [Including Video, Audio, and Captions in Outputs in AWS Elemental MediaConvert](video-audio-captions-selectors.md)
   + [HLS Player Version Support](hls-player-version-support.md)
+ [Setting Up Audio in AWS Elemental MediaConvert Jobs](setting-up-audio.md)
   + [About Audio Selectors](about-audio-selectors.md)
+ [Setting Up Captions in AWS Elemental MediaConvert Jobs](including-captions.md)
   + [Gathering Required Captions Information](gather-required-captions-information.md)
   + [Creating Input Captions Selectors](create-input-caption-selectors.md)
      + [QuickTime Captions Track or Captions in MXF VANC Data (Ancillary)](ancillary.md)
      + [CEA/EIA-608, CEA/EIA-708 (Embedded)](embedded.md)
      + [DVB-Sub](dvb-sub-or-scte-27.md)
      + [Teletext](dvb-teletext.md)
      + [SCC, SRT, STL, TTML (Sidecar)](scc.md)
   + [Setting Up Captions in Outputs](set-up-captions-in-outputs.md)
      + [TTML and WebVTT (ABR) Output Captions](ttml-and-webvtt-output-captions.md)
      + [CEA/EIA-608 and CEA/EIA-708 (Embedded) Output Captions](embedded-output-captions.md)
      + [DVB-Sub and Teletext Output Captions](dvb-sub-and-teletext-output-captions.md)
      + [SCC, SRT (Sidecar) Output Captions](scc-srt-output-captions.md)
      + [Burn-In Output Captions](burn-in-output-captions.md)
+ [Working with Queues](working-with-queues.md)
   + [Creating a Queue in AWS Elemental MediaConvert](creating-queues.md)
   + [Pausing and Reactivating Queues in AWS Elemental MediaConvert](updating-queue-status.md)
   + [Listing and Viewing Queues in AWS Elemental MediaConvert](listing-queues.md)
   + [Deleting an AWS Elemental MediaConvert Queue](deleting-a-queue.md)
+ [Setting Up Timecodes](setting-up-timecode.md)
   + [Adjusting the Job-wide Timecode Configuration](timecode-jobconfig.md)
   + [Adjusting the Input Timecode Setting](timecode-input.md)
   + [Adjusting the Output Timecode Settings](timecode-output.md)
+ [Including SCTE-35 Markers in AWS Elemental MediaConvert Outputs](including-scte-35-markers.md)
   + [Including SCTE-35 Markers in an Output](including-scte-35-markers-in-an-output.md)
   + [Including SCTE-35 Information in Your HLS Manifest](including-scte-35-information-in-your-hls-manifest.md)
   + [Blanking Out Content from Ad Avails](ad-avail-blanking.md)
+ [Using Encryption in AWS Elemental MediaConvert](using-encryption.md)
+ [Setting Up a Job for HDR](hdr.md)
   + [Correcting Input Color Space Metadata](correcting-input-color-space-metadata.md)
   + [Inserting Color Metadata in the Output](inserting-color-metadata-in-the-output.md)
   + [Correcting Color in the Output](correcting-color-in-the-output.md)
+ [Including Graphic Overlays with AWS Elemental MediaConvert Image Inserter](graphic-overlay.md)
+ [Transcoding Only a Portion of Your Input (Input Clipping)](input-clipping-stitching.md)
+ [Supported Input Codecs and Containers](reference-codecs-containers-input.md)
+ [Supported Output Codecs and Containers](reference-codecs-containers.md)
+ [Captions Support Tables by Output Container Type](captions-support-tables-by-container-type.md)
+ [Example Job Settings](example-job-settings.md)
+ [Postman Collection Files](postman-collection-files.md)
+ [Monitoring AWS Elemental MediaConvert Jobs](monitoring-overview.md)
   + [CloudWatch Metrics](MediaConvert-metrics.md)
+ [Working with CloudWatch Events and AWS Elemental MediaConvert](cloudwatch_events.md)
   + [Tutorial: Setting Up Email Notifications for Failed Jobs](mediaconvert_sns_tutorial.md)
   + [AWS Elemental MediaConvert Events](mediaconvert_cwe_events.md)
+ [Logging AWS Elemental MediaConvert API Calls with AWS CloudTrail](logging-using-cloudtrail.md)
+ [Document History for User Guide](doc-history.md)
+ [AWS Glossary](glossary.md)