---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, March 2023 release
description: Latest release of Adobe Experience Manager Guides as a Cloud Service

---
# March release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the latest release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.2.235.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the latest release of AEM Guides as a Cloud Service.

## Steps to index the existing content (Only if you are on a version prior to September release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

* Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed || Example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(For example: http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service March 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.03.0| 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 | 
|  |  |  |  |


## New features and enhancements

AEM Guides as a Cloud Service provides enhancements and new features in the latest release:

### Open and play video or audio files in the Web Editor

AEM Guides now provides the feature to open and play the audio or video files in the Web Editor. You can change the volume or the view of the video. In the shortcut menu, you  also have the options to **Download**, change **Play back Speed**, or view **Picture in Picture**.

<img  src ="assets/video-web-editor.png" alt="play video" width=600>


## Fixed issues

The bugs fixed in various areas are listed below:

* Download PDF process is not working appropriately in the Web Editor. (11496)
* JSON output | Map metadata having property value as `"value in spaces and double quotes"` leads to a publishing error. (11438)
*  Insertion for audio and video multimedia files fails in the YouTube format under the **Insert Multimedia** icon. (11320)
* Validation error occurs when a map is created using the  template which has a specialized title element. (11212)
* Native PDF | footnote present in table header leads to bold and center-aligned text in the corresponding page footer within the PDF output. (10610) 
>[!NOTE]
>
>To reflect the Native PDF change, delete the PDF folder located at /content/dam/dita-templates and then upgrade to the latest build. (10610)

