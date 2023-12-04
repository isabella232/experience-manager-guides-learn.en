---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, April 2023 release
description: April 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# April 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version April 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in April 2023 release of AEM Guides as a Cloud Service](whats-new-2023.4.0.md).

## Upgrade to the April 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.4.249.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the April 2023 release of AEM Guides as a Cloud Service.

## Steps to index the existing content (Only if you are on a version prior to September release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and using the new find and replace text at map level:

* Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed || Example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(For example: http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service April 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.04.0| 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 | 
|  |  |  |  |



## Fixed issues

The bugs fixed in various areas are listed below:

* Native PDF | Publishing content that has an output class with brackets() leads to a publishing freeze. (11596)
* Issue occurs on moving (drag and drop) in place of an existing list item with Track Changes on. (11570)
* Issue occurs on moving (drag and drop) as a new list item with Track Changes on. (11569)
* Indent or outdent list items does not work as expected with Track Changes on. (11568)
* Adding content on a line with  Track Changes on, and then turning off Track Changes does not actually turn it off. (11567)
* Difficulty in dragging and dropping a list-item, text is moved in place of the list-item. (11566)
* Completed review does not open in read only mode. (11387)
* Issue occurs in AEM Site search (doesn't work beyond 2-3 level nodes). (11352)
* On authoring in the element displayed in green (Track Changes,) the new content is displayed as track change even though the track change is disabled. (7021)

### Known issue with workaround

Adobe has identified the following known issue for AEM Guides as a Cloud Service April 2023 release.

* Native PDF | The old metadata is not populated until the output preset is explicitly opened.
