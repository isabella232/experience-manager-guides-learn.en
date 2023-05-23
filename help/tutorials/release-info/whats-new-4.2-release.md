---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.2 release
description: Learn the new and enhanced features in 4.2 releases of Adobe Experience Manager Guides
---
# What's new in 4.2 release of Adobe Experience Manager Guides (February 2023)

This article covers the new and enhanced features in version 4.2 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-4.2.md) article.

## Generate reports from the Web Editor

AEM Guides comes with a feature in the Web Editor that enables you to check the overall completeness of your technical documents and generate reports for them.
You can view the topic list and manage the metadata of all references for the current map from the
**Reports** tab in the Web Editor.

**Generate the Topic List view**

You can generate the Topic List which provides detailed information about your topics, such as the reference type, document state, and author. You can also generate the CSV to download the current snapshot of the topics in the DITA map.

**Manage metadata and change document state**

You can apply tags on an individual topic or use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or a sub-map. You can also change the document state of all selected topics to the next possible common document state.

<img  src="assets/web-editor-metadata-panel.png" alt="manage metadata" width=600>

## Revamped UX for the review functionality

Now AEM guides provides an improved UX that helps you review the topics shared for review. In the latest experience, the review functionality has the following enhancements:

* Refreshed user interface
* Conditions panel that allows you to highlight the content as per the available conditions in the topic.
* Each comment in the comment panel is linked to the corresponding text in the current topic. It helps you identify the commented text. 
* The comments are displayed in the order of the commented text in the document. 
* Name of the review task is displayed on the review workflow.
* Select the rootmap for the review task which is used to resolve all the key references and glossary terms used in the review content.
* Contextual toolbar which helps you quickly highlight or strikethrough text.
* Options menu to edit or delete your own comments.
* For outdated comments, you have access to side-by-side view which helps you compare the previous version of the topic with current review version
* On using the filters, the comments on the right panel get filtered according to the selection, and the
number of comments in the left panel is updated accordingly.


<img alt="review task" src="assets/comment-pop-up-panel.png" width=600>


For more details, refer to the *Review topics or maps* section in the Using Adobe Experience Manager Guides guide.

## Translation enhancements

Now you have more user-friendly enhancements in the Translation dashboard which help you easily translate your documents from the Web Editor.


**Version Label column added to the translation dashboard**

In the translation dashboard, you can also see the Version Label column. This displays the Label for the selected version of the source file. This can help you select all files with a specific label and translate them in one go.

**View version difference for Out of Sync files from the translation dashboard**

Now you can check the differences between the selected version and the last translated source version of the topics. You can also choose to translate the **Out of Sync** files based on the changes done between the two versions of a topic.

<img  src="assets/translation-version-diff.png" alt="translation board" width=600>



**Pass the version label to the target version**

AEM Guides allows you to pass the label of the source file to the target file. This helps you easily identify the source version for the translated file.

<img alt="translation labels" src="assets/translation-pass-source-label.png" width=600>

For example, if you have some source files with the version label Release 1.0 applied to them, then you can also pass on the source label (Release 1.0) to the translated file.

**Force sync for out of sync assets**

If you make changes in some of the assets, then AEM Guides marks them to be Out of Sync. You can either re-translate the modified assets or choose to dismiss Out of Sync status. For example, if you have made some minor changes that really don't need a translation you can mark their status as In Sync.

**View In Progress translation projects for a topic or map**

Some of the references on your translation dashboard might be in progress. Now AEM Guides provides a feature to help you view the list of all In Progress translation projects (along with the target language) that contain the selected reference.

For more details, refer to the *Translate documents from the Web Editor* section in the Using Adobe Experience Manager Guides guide.

## Generate output in various formats from the Web Editor

Now you can easily generate the output for your topics or DITA map from the Web Editor. You can configure various output presets like AEM Site, PDF, HTML5,
JSON (a headless output format), and custom output. Use these to generate the respective outputs. You can define attributes in your DITA topics and then use the condition preset to apply a condition while publishing the output. You can also use the Baseline publishing feature to selectively publish a specific version of your DITA map or topic.

**Manage Global and Folder Profile output presets**

AEM Guides provide you the feature to create and manage output presets for the Global and Folder Profiles. Then you can easily use these output presets to generate output for all maps that are related to that Global or Folder profile.

<img alt="add preset" src="assets/add-global-output-preset.png" width=400>


These global presets appear under the **Output** tab of all related maps. You can use them to generate the output for all the related maps. You can select the preset as the default PDF preset to generate the PDF output. You can also **Edit**, **Rename**, **Duplicate**, or **Delete** an existing output preset from the **Options** menu.

>[!NOTE]
>
>Only folder level administrative users can create Global and Folder Profile presets.

## Find and replace the text at map level

You can now search for files within a map that contain specific text. The searched text is highlighted in the files. You can also replace the searched word or phrase with another word or phrase within the files. Select the **Replace single occurrence** icon to replace the current occurrence and the **Replace all in File** icon to replace all occurrences in the selected file. You can select **Replace All** icon to replace all occurrences of the searched term in all the files.

<img src="assets/map-find-replace.png" alt="map find replace" width=600>

 
By default, the options **Checkout file before replace** and **Create new version after replace** are selected, so a file is checked out before you replace the text, and a new version is created after the text is replaced. You can also search the string in the indirect references within the DITA map. By default, this is disabled so the search is performed only on the direct references.

## Layout view in the Map Editor


Now you can view the complete layout of a DITA map in the Map Editor. When you open a map for editing, it opens the Layout view of the Map Editor. In this view, you can see the map hierarchy in a tree view. You can also edit and organize or structure the topics in a map.

<img src="assets/layout-view-map.png" alt=" map layout view" width=600>

The Layout view contains a separate toolbar which helps you perform many tasks on the topics present in a map. 
You can insert topic references, topic group, key definitions in a map. You can reorganize the topics present in a map by moving them up, down, left, or right. You can also drag-and-drop the topics to move them in a map. The Map Editor also provides the icons to lock or unlock files, check the version history, and do a version label management.


The Layout view also provides the **View Options** to show or hide line number, show, or hide check box, or show the file name or title for the topics in a map.
You can also view the topics based on the conditional filters applied on them.

In addition to organizing topics in the map file, you can also add, move, copy, paste, or delete references using the **Options** menu available for an element in the Layout view. 

<img src="assets/layout-inline-attributes.png" alt=" map layout attributes" width=600> 


The right panel displays the Content Properties and the Map Properties in the Layout view of the Map Editor. Now you can also set the metadata information for the topics or the map. You can define the Nav Title, Link Text, Short Description, and Keywords for the selected topic or map.
 
For more details, see *Layout view* section in the Using Adobe Experience Manager Guides guide.

## Quick Generate panel

Now AEM Guides provides the Quick Generate panel which helps you quickly generate and view the output for presets created for your DITA map.

<img src="assets/quick-generate-map-view.png" alt=" quick generate panle" width=600> 
 
In the **Quick Generate** panel, you can see the list of all the output presets created for your DITA map. You can also quickly view the output generated for the presets. A success or failure message is displayed on the completion of output generation. You can also view the error log which contains details of the error that occurred in the generation process.

## Create a dynamic baseline based on labels

Now AEM Guides provides you the feature to create dynamic baselines based on labels. If you generate a baseline, download a baseline, or create a translation project using a baseline, the files are picked dynamically based on the updated labels. This feature is handy as you don't have to modify the baseline when updating the labels.
 
<img src="assets/dynamic-baseline.png" alt=" dynamic baseline" width=400> 

## Delete and Duplicate files from the repository panel

Now you can easily delete files (single file at a time) from the **Options** menu of the selected file from repository panel. A confirmation prompt is displayed before deleting the file. If the file is not referenced from any other file, it is deleted, and a success message is displayed. 

<img src="assets/options-menu-repo-view-file-level.png" alt="file options menu " width=500> 

You can also create a duplicate or a copy of the selected file. By default, the file is created with
a suffix (like filename_1.extension).


## Other Web Editor enhancements

* In AEM Guides, you can perform some common operations for images and media files using the context menu. Now you can also locate the selected image or media in the repository or view the preview of the file in Assets UI.

* The name of the current Folder Profile is displayed as a label for the User Preferences icon in the main toolbar. This helps you identify the folder profile you are working on.

* When you open a map in the map view, the title of the current map is displayed in the center of the main toolbar. This is helpful to let the users know which map is currently open.

## Purging selected versions of files

As you create and maintain your content, many versions might get created for your DITA files in your repository. AEM Guides allows you to purge older versions of your DITA files from the repository and free up disk space.

<img  src="assets/preview-purge-report.png" alt="Preview purge report" width=500>
 
AEM Guides does not delete the first version of the file or a version that is included in a baseline, or has a label applied to it. Purge operation doesn't even delete files that are included in a translation or a review workflow. You can choose the number of versions to retain and also decide to delete the files which are older than the defined number of days.

Before starting the purge operation, you can preview the report to see the versions that will be purged. You can then decide to start or cancel the purge operation.

<img  src="assets/download-purge-report.png" alt="PDownload purge report" width=500>

Once the purge operation is complete, you can check the purge report to see the purged files.

## View title in place of UUID in the Oxygen Editor

Now AEM Guides allows you to choose **Use Title in Editor and Maps Manager** option in Settings. If you select this option, the title of the file is displayed on the file's tab when opened in the Editor or the DITA Maps Manager. If you do not select this option, then the UUID of the file is displayed on the file's tab.

## Metadata UI available for PDF Presets

You can set the metadata from the output preset of a DITA map. You can set the Title, Author, Subject, and Keywords metadata. This metadata is mapped to the metadata in the File Properties of your output PDF. This metadata overrides the metadata defined at the book level. You can define the metadata specifically in each output preset and pass it on to the output PDF.

## Native PDF | PDF with change bar showing the difference between document versions

Now you can create a PDF that shows the differences in content between two versions using change bar. You can choose to compare the current version with a baseline of the previous version or compare between the two selected baseline versions.

<img  src="assets/pdf-change-version.png" alt="pdf-change-version" width=600>
 
A change bar appears in the PDF to indicate the modified, inserted, or deleted content. You also have the options to do the following:
* Show the inserted content in green color and underlined
* Show the deleted content in red color and marked with a strikethrough

## Native PDF | Variable support for Output Path and PDF File name

Now you can also use the following out-of-box variables to define the Output Path and PDF File. You can use a single or a combination of variables to define these options:
* `${map_filename}`
* `${map_title}`
* `${preset_name}` 
* `${language_code}` 
* `${map_parentpath}` (Only for Output Path)
* `${path_after_langfolder}` (Only for Output Path)

## Native PDF | Generate Table of Contents for DITA maps and reorder page layouts

Now you can also generate the TOC in DITA maps using an advanced PDF setting of the template. You can choose to enable or disable the display of the various page layouts and also reorder their position.

## Native PDF | Add a custom bookmark in PDF output

Now you can add a custom bookmark on a particular content in your final PDF output for easy navigation. This would be added to the TOC  which is created from the topic or section titles in your DITA map. 

## Native PDF | Apply custom style on TOC entries and topic content  

AEM Guides provides the feature to apply custom styling on the TOC entries or a particular topic in the PDF output. For example, you can change color of the text in the TOC and the topic's title. You can also apply styles on the entire content within the topic.
