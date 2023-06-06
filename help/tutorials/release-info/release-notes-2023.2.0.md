---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, February 2023 release
description: February release of Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
---
# February 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version February 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in February 2023 release of AEM Guides as a Cloud Service](whats-new-2023.2.0.md).

## Upgrade to the February 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.2.235.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the February 2023 release of AEM Guides as a Cloud Service.

## Steps to index the existing content (Only if you are on a version prior to September release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

* Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed || Example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(For example: http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service February 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Not compatible | 2022 or higher |
| | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.02.0| 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 | 
|  |  |  |  |

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

* Changes in the Web Editor html cause issues with `<dl>` and `<dlentry>`. (11024)
* Some attributes are not being treated as conditional and causing issues. (10895)
* Three levels or more nested `<indexterm>` are not nested in native PDF export. (10799)
* The content disappears in the body of a task on switching from Author to Source view. (10735)
* Review comments are misplaced in a review task. (10625)
* **Undo** or **Redo** is not working correctly on some files. (10373)
* Custom metadata is not getting retained on copy and paste action. (10367) 
* Undo option in XML Editor takes the user to the top of the page. (10091) 
* Node properties are removed after copy and paste operation of an asset. (10053)
* mimeType is hardcoded for DITA assets creation and update. (8979)
* Version creator name in Version History is "fmdita-serviceuser" for the files uploaded via Assets UI. (8910)
* Content fragments cannot be copied and pasted when AEM Guides is installed on Cloud. (11315)
* The browser (Web Editor) freezes on loading content with custom schema. (11211)

### Management

* Copying a DITA map Asset (from Asset UI ) causes erroneous baselines in the copied asset. (11218)
* Warning message is not displayed on the upload of a file that is larger than the limit allowed in AEM (2 GB by default). (10817)
* Web Editor-Baseline | The behavior of the Latest column is different in the new baseline dashboard within the Web Editor. (10808)
* Translation | Translation job does not get started due to invalid /libs/fmdita/i18n/ja.json. (10543)
* Translation | An error occurs in a scoping translation project created from the translation dashboard (Human Translation). (10526)
* Translation | Post processing is blocked for the entire language folder whose assets are present in an active translation project. (10332)
* Multiple pop-ups appear for any asset if the version is changed and saved on Baseline editor. (10399)
* Session Leak occurs at `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publishing

* Topic regeneration is not working for some scenarios. (10635)
* Publishlistener does not display the requested data in info logs, and it also contains some junk logs.( 10567)
* Native PDF | On creating an output preset with "Add to Folder Profile" option, PDF generation fails with a Null Pointer exception. (10950)
* Native PDF | Issues occur on rotating the Table header. (10555)
* Native PDF | Nested `<indexterm>` are not nested in native PDF export. (10521)
* Native PDF | Nested topicref in appendices are all transformed to h1 in the temporary HTML. (10454)
* Baseline publishing fails for PDF generated using FrameMaker Publishing Server 2020. (10551)
* Native PDF | Adding `xref` to an Image does not render the image on the generated PDF. (11346)
* Native PDF | Image tag adds display-inline attribute to all the images. (10653)
* Native PDF | Draft comments are hidden by default in the generated output. (10560) 
* Native PDF | navtitle is not honored for topichead. (10509)
