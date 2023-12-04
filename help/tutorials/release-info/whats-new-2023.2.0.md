---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, February 2023 release
description: February release of Adobe Experience Manager Guides as a Cloud Service
---
# What's new in February 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in version February 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-2023.2.0.md) article.


## Generate reports from the Web Editor

AEM Guides comes with a feature in the Web Editor that enables you to check the overall completeness of your technical documents and generate reports for them.
You can view the topic list, manage the metadata, and see the multimedia used in all references for the current map from the
**Reports** tab in the Web Editor.

**Generate the Topic List view**

You can generate the Topic List which provides detailed information about your topics, such as the reference type, document state, and author. You can also generate the CSV to download the current snapshot of the topics in the DITA map.

**Manage metadata and change document state**

You can apply tags on an individual topic or use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or a sub-map. You can also change the document state of all selected topics to the next possible common document state.

<img  src="assets/web-editor-metadata-panel.png" alt="manage metadata" width=600>

**Generate the Multimedia  report**

You can generate the multimedia report which contains detailed information about the multimedia used in your references within the current map. You have the flexibility to filter and sort the multimedia files listed in the report.
You can also generate the CSV to download the current snapshot of the multimedia used in the DITA map.

<img  src="assets/web-editor-reports-multimedia.png" alt="multimedia report" width=600>

## Revamped UX for the review functionality

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



## Translation enhancements

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


## Generate output in various formats from the Web Editor

Now you can easily generate the output for your topics or DITA map from the Web Editor. You can configure various output presets like AEM Site, PDF, HTML5,
JSON (a headless output format), and custom output. You can then use these to generate the respective outputs. 

You can define attributes in your DITA topics and then use the condition preset to apply a condition while publishing the output. You can also use the Baseline publishing feature to selectively publish a specific version of your DITA map or topic.


## Find and replace the text at map level

AEM Guides allows you to search for files within a map that contain specific text. The searched text is highlighted in the files. Now you can also replace the searched word or phrase with another word or phrase within all the files. You can select **Replace All** icon  on the right at the top of the list to replace all occurrences of the searched term in all the files.

<img src="assets/map-find-replace.png" alt="map find replace" width=600>

## Delete and Duplicate files from the repository panel

Now you can easily create a duplicate or a copy of a file from the **Options** menu of the selected file in the repository panel. By default, the file is created with
a suffix (like `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="file options menu " width=500> 


## Other Web Editor enhancements

* In AEM Guides, you can perform some common operations for images and media files using the context menu. Now you can also locate the selected image or media in the repository or view the preview of the file in Assets UI.

* The name of the current Folder Profile is displayed as a label for the User Preferences icon in the main toolbar. This helps you identify the folder profile  you are working on.

* When you open a map in the map view, the title of the current map is displayed in the center of the main toolbar. This is helpful to let the users know which map is currently open.


## View title in place of UUID in the Oxygen Editor

Now AEM Guides allows you to choose **Use Title in Editor and Maps Manager** option in Settings. If you select this option, the title of the file is displayed on the file's tab when opened in the Editor or the DITA Maps Manager. If you do not select this option, then the UUID of the file is displayed on the file's tab.

## Microservice-based publishing for AEM Guides as a Cloud Service

The new publishing microservice enables you to run large publishing workloads concurrently on AEM Guides as a Cloud Service and leverage the industry leading Adobe I/O Runtime serverless platform.

For each publishing request AEM Guides as a Cloud Service runs a separate container which scales horizontally as per the user requests. This enables you  to run multiple publishing requests and get an improved  performance.

For more details, see [Configure new microservice-based publishing for AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## Native PDF | Add a custom bookmark in PDF output

Now you can add a custom bookmark on a particular content in your final PDF output for easy navigation. This would be added to the TOC  which is created from the topic or section titles in your DITA map. 

## Native PDF | Apply custom style on TOC entries and topic content  

AEM Guides provides the feature to apply custom styling on the TOC entries or a particular topic in the PDF output. For example, you can change color of the text in the TOC and the topic's title. You can also apply styles on the entire content within the topic.


## Native PDF | Style the page marker in footnote component

Now you can style the page marker in the foot notes. For example, you can add brackets or change their color. These styles help the users easily identify the page markers in the document.

## Native PDF | Change bar to indicate changed topics in Table of Contents

AEM Guides  now allows you to quickly identify the changed topics in the TOC of the PDF output.  It shows a change bar on the left of the changed topics in the TOC. You can click on the topic in the TOC and view the detailed changes.

<img src="assets/change-marker-toc.png" alt="Change marker in TOC " width=500>
