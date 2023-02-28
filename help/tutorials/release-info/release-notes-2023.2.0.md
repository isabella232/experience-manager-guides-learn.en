---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, February 2023 release
description: Latest release of Adobe Experience Manager Guides as a Cloud Service
---
# Latest release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the latest release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.11.198.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the latest release of AEM Guides as a Cloud Service.

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


## New features and enhancements

AEM Guides as a Cloud Service provides enhancements and new features in the latest release:

### Generate reports from the Web Editor

AEM Guides comes with a feature in the Web Editor that enables you to check the overall completeness of your technical documents and generate reports for them.
You can view the topic list, manage the metadata, and see the multimedia used in all references for the current map from the
**Reports** tab in the Web Editor.

**Generate the Topic List view**

You can generate the Topic List which provides detailed information about your topics, such as the reference type, document state, and author. You can also generate the CSV to download the current snapshot of the topics in the DITA map.

**Manage metadata and change document state**

You can apply tags on an individual topic or use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or a sub-map. You can also change the document state of all selected topics to the next possible common document state.

<img  src="assets/web-editor-metadata-panel.png" alt="manage metadata" width=600>

**Generate the Multimedia  report**

You can generate the multimedia report which contains detailed information about the multimedia used in your references within the current mail. You also have the flexibility to filter and sort the multimedia files in this report.
You can generate the CSV to download the current snapshot of the topics in the DITA map.

<img  src="assets/web-editor-reports-multimedia.png" alt="multimedia report" width=600>

### Revamped UX for the review functionality

Now AEM guides provides an improved UX that helps you review the topics shared for review. In the latest experience, the review functionality has the following enhancements:

* Refreshed user interface
* Conditions panel that allows you to highlight the content as per the available conditions in the topic
* Each comment in the comment panel is linked to the corresponding text in the current topic. It helps you identify the commented text. 
* The comments are displayed in the order of the commented text in the document. 
* Name of the review task is displayed on the review workflow.
* Select the rootmap for the review task which is used to resolve all the key references and glossary terms used in the review content.
* Contextual toolbar which helps you quickly highlight or strikethrough text
* Options menu to edit or delete your own comments
* For outdated comments, you have access to side-by-side view which helps you compare the previous version of the topic with current review version.
* On using the filters, the comments on the right panel get filtered according to the selection, and the
number of comments in the left panel is updated accordingly.


    <img alt="review task" src="assets/comment-pop-up-panel.png" width=600>



### Translation enhancements

Now you have more user-friendly enhancements in the Translation dashboard which help you easily translate your documents from the Web Editor.

**Pass the version label to the target version**

AEM Guides allows you to pass the label of the source file to the target file. This helps you easily identify the source version for the translated file.

<img alt="translation labels" src="assets/translation-pass-source-label.png" width=600>

For example, if you have some source files with the version label Release 1.0 applied to them, then you can also pass on the source label (Release 1.0) to the translated file.

**Force sync for out of sync assets**

If you make changes in some of the assets, then AEM Guides marks them to be Out of Sync. You can either re-translate the modified assets or choose to dismiss Out of Sync status. For example, if you have made some minor changes that really don't need a translation you can mark their status as In Sync.

<img  src="assets/translation-version-diff.png" alt="translation board" width=600>

**View In Progress translation projects for a topic or map**

Some of the references on your translation dashboard might be in progress. Now AEM Guides provides a feature to help you view the list of all In Progress translation projects (along with the target language) that contain the selected reference.


### Generate output in various formats from the Web Editor

Now you can easily generate the output for your topics or DITA map from the Web Editor. You can configure various output presets like AEM Site, PDF, HTML5,
JSON (a headless output format), and custom output. You can then use these to generate the respective outputs. 

You can define attributes in your DITA topics and then use the condition preset to apply a condition while publishing the output. You can also use the Baseline publishing feature to selectively publish a specific version of your DITA map or topic.


### Find and replace the text at map level

AEM Guides allows you to search for files within a map that contain specific text. The searched text is highlighted in the files. Now you can also replace the searched word or phrase with another word or phrase within all the files. You can select **Replace All** icon  on the right at the top of the list to replace all occurrences of the searched term in all the files.

<img src="assets/map-find-replace.png" alt="map find replace" width=600>

### Delete and Duplicate files from the repository panel

Now you can easily create a duplicate or a copy of a file from the **Options** menu of the selected file in the repository panel. By default, the file is created with
a suffix (like `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="file options menu " width=500> 


### Other Web Editor enhancements

* In AEM Guides, you can perform some common operations for images and media files using the context menu. Now you can also locate the selected image or media in the repository or view the preview of the file in Assets UI.

* The name of the current Folder Profile is displayed as a label for the User Preferences icon in the main toolbar. This helps you identify the folder profile  you are working on.

* When you open a map in the map view, the title of the current map is displayed in the center of the main toolbar. This is helpful to let the users know which map is currently open.


### View title in place of UUID in the Oxygen Editor

Now AEM Guides allows you to choose **Use Title in Editor and Maps Manager** option in Settings. If you select this option, the title of the file is displayed on the file's tab when opened in the Editor or the DITA Maps Manager. If you do not select this option, then the UUID of the file is displayed on the file's tab.

### Configure new microservice-based publishing for AEM Guides as a Cloud Service

The new publishing microservice enables you to run large publishing workloads concurrently on AEM Guides as a Cloud Service and leverage the industry leading Adobe I/O Runtime serverless platform.

For each publishing request AEM Guides as a Cloud Service runs a separate container which scales horizontally as per the user requests. This enables you  to run multiple publishing requests and get an improved  performance.

For more details, see [Configure new microservice-based publishing for AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

### Native PDF | Add a custom bookmark in PDF output

Now you can add a custom bookmark on a particular content in your final PDF output for easy navigation. This would be added to the TOC  which is created from the topic or section titles in your DITA map. 

### Native PDF | Apply custom style on TOC entries and topic content  

AEM Guides provides the feature to apply custom styling on the TOC entries or a particular topic in the PDF output. For example, you can change color of the text in the TOC and the topic's title. You can also apply styles on the entire content within the topic.


### Native PDF | Style the page marker in footnote component

Now you can style the page marker in the foot notes. For example, you can add brackets or change their color. These styles help the users easily identify the page markers in the document.

### Native PDF | Change bar to indicate changed topics in Table of Contents	 

AEM Guides  now allows you to quickly identify the changed topics in the TOC of the PDF output.  It shows a change bar on the left of the changed topics in the TOC. You can click on the topic in the TOC and view the detailed changes.

<img src="assets/change-marker-toc.png" alt="Change marker in TOC " width=500> 

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
