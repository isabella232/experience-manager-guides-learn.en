---
title: Release Notes | Adobe Experience Manager Guides 4.2 release
description: Latest release of Adobe Experience Manager Guides

---
# 4.2 release of Adobe Experience Manager Guides (February 2023)

This release note covers the upgrade instructions, new features, and enhancements in version 4.2 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

## Upgrade to the latest release

You can easily upgrade your current version of AEM Guides to version 4.2. Before you proceed with upgrading to version 4.2 of AEM Guides, you must consider the following points:
* If you are using version 4.0, 4.1, or 4.1.x, then you can directly upgrade to version 4.2.
* If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
* If you are on a version prior to 3.8.5, refer to the *Upgrade AEM Guides* section in the product-specific installation guide.

>[!NOTE]
>
>You must install AEM service pack before upgrading AEM Guides version.

For details, see [Upgrade instructions](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4.2 | Release notes

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.2 release. 

### Adobe Experience Manager

**Non-UUID**
Version 6.5 Service Pack 15, 14, 13, or 12

**UUID**
Version 6.5 Service Pack 15, 14, 13, or 12

For more details, see the *Technical requirements* section in the Install and configure Adobe Experience Manager Guides guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.2 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
| 4.2 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.2 (Non-UUID)|  2.1-regular-4 | 2.1-regular-4 |  1.6 | 1.6  |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8  |2.3 | 2.3  |
|  |  |   |  


## New features and enhancements

AEM Guides provides many enhancements and new features in the 4.2 release:

### Generate reports from the Web Editor

AEM Guides comes with a feature in the Web Editor that enables you to check the overall completeness of your technical documents and generate reports for them.
You can view the topic list and manage the metadata of all references for the current map from the
**Reports** tab in the Web Editor.

**Generate the Topic List view**

You can generate the Topic List which provides detailed information about your topics, such as the reference type, document state, and author. You can also generate the CSV to download the current snapshot of the topics in the DITA map.

**Manage metadata and change document state**

You can apply tags on an individual topic or use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or a sub-map. You can also change the document state of all selected topics to the next possible common document state.

<img  src="assets/web-editor-metadata-panel.png" alt="manage metadata" width=600>

### Revamped UX for the review functionality

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

### Translation enhancements

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

### Generate output in various formats from the Web Editor

Now you can easily generate the output for your topics or DITA map from the Web Editor. You can configure various output presets like AEM Site, PDF, HTML5,
JSON (a headless output format), and custom output. Use these to generate the respective outputs. You can define attributes in your DITA topics and then use the condition preset to apply a condition while publishing the output. You can also use the Baseline publishing feature to selectively publish a specific version of your DITA map or topic.

**Manage Global and Folder Profile output presets**

AEM Guides provide you the feature to create and manage output presets for the Global and Folder Profiles. Then you can easily use these output presets to generate output for all maps that are related to that Global or Folder profile.

<img alt="add preset" src="assets/add-global-output-preset.png" width=400>


These global presets appear under the **Output** tab of all related maps. You can use them to generate the output for all the related maps. You can select the preset as the default PDF preset to generate the PDF output. You can also **Edit**, **Rename**, **Duplicate**, or **Delete** an existing output preset from the **Options** menu.

>[!NOTE]
>
>Only folder level administrative users can create Global and Folder Profile presets.

### Find and replace the text at map level

You can now search for files within a map that contain specific text. The searched text is highlighted in the files. You can also replace the searched word or phrase with another word or phrase within the files. Select the **Replace single occurrence** icon to replace the current occurrence and the **Replace all in File** icon to replace all occurrences in the selected file. You can select **Replace All** icon to replace all occurrences of the searched term in all the files.

<img src="assets/map-find-replace.png" alt="map find replace" width=600>

 
By default, the options **Checkout file before replace** and **Create new version after replace** are selected, so a file is checked out before you replace the text, and a new version is created after the text is replaced. You can also search the string in the indirect references within the DITA map. By default, this is disabled so the search is performed only on the direct references.

### Layout view in the Map Editor


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

### Quick Generate panel

Now AEM Guides provides the Quick Generate panel which helps you quickly generate and view the output for presets created for your DITA map.

<img src="assets/quick-generate-map-view.png" alt=" quick generate panle" width=600> 
 
In the **Quick Generate** panel, you can see the list of all the output presets created for your DITA map. You can also quickly view the output generated for the presets. A success or failure message is displayed on the completion of output generation. You can also view the error log which contains details of the error that occurred in the generation process.

### Create a dynamic baseline based on labels

Now AEM Guides provides you the feature to create dynamic baselines based on labels. If you generate a baseline, download a baseline, or create a translation project using a baseline, the files are picked dynamically based on the updated labels. This feature is handy as you don't have to modify the baseline when updating the labels.
 
<img src="assets/dynamic-baseline.png" alt=" dynamic baseline" width=400> 

### Delete and Duplicate files from the repository panel

Now you can easily delete files (single file at a time) from the **Options** menu of the selected file from repository panel. A confirmation prompt is displayed before deleting the file. If the file is not referenced from any other file, it is deleted, and a success message is displayed. 

<img src="assets/options-menu-repo-view-file-level.png" alt="file options menu " width=500> 

You can also create a duplicate or a copy of the selected file. By default, the file is created with
a suffix (like filename_1.extension).


### Other Web Editor enhancements

* In AEM Guides, you can perform some common operations for images and media files using the context menu. Now you can also locate the selected image or media in the repository or view the preview of the file in Assets UI.

* The name of the current Folder Profile is displayed as a label for the User Preferences icon in the main toolbar. This helps you identify the folder profile you are working on.

* When you open a map in the map view, the title of the current map is displayed in the center of the main toolbar. This is helpful to let the users know which map is currently open.

### Purging selected versions of files

As you create and maintain your content, many versions might get created for your DITA files in your repository. AEM Guides allows you to purge older versions of your DITA files from the repository and free up disk space.

<img  src="assets/preview-purge-report.png" alt="Preview purge report" width=500>
 
AEM Guides does not delete the first version of the file or a version that is included in a baseline, or has a label applied to it. Purge operation doesn't even delete files that are included in a translation or a review workflow. You can choose the number of versions to retain and also decide to delete the files which are older than the defined number of days.

Before starting the purge operation, you can preview the report to see the versions that will be purged. You can then decide to start or cancel the purge operation.

<img  src="assets/download-purge-report.png" alt="PDownload purge report" width=500>

Once the purge operation is complete, you can check the purge report to see the purged files.

### View title in place of UUID in the Oxygen Editor

Now AEM Guides allows you to choose **Use Title in Editor and Maps Manager** option in Settings. If you select this option, the title of the file is displayed on the file's tab when opened in the Editor or the DITA Maps Manager. If you do not select this option, then the UUID of the file is displayed on the file's tab.

### Metadata UI available for PDF Presets

You can set the metadata from the output preset of a DITA map. You can set the Title, Author, Subject, and Keywords metadata. This metadata is mapped to the metadata in the File Properties of your output PDF. This metadata overrides the metadata defined at the book level. You can define the metadata specifically in each output preset and pass it on to the output PDF.

### Native PDF | PDF with change bar showing the difference between document versions

Now you can create a PDF that shows the differences in content between two versions using change bar. You can choose to compare the current version with a baseline of the previous version or compare between the two selected baseline versions.

<img  src="assets/pdf-change-version.png" alt="pdf-change-version" width=600>
 
A change bar appears in the PDF to indicate the modified, inserted, or deleted content. You also have the options to do the following:
* Show the inserted content in green color and underlined
* Show the deleted content in red color and marked with a strikethrough

### Native PDF | Variable support for Output Path and PDF File name

Now you can also use the following out-of-box variables to define the Output Path and PDF File. You can use a single or a combination of variables to define these options:
* ${map_filename}
* ${map_title}
* ${preset_name}
* ${language_code}
* ${map_parentpath} (Only for Output Path)
* ${path_after_langfolder} (Only for Output Path)

### Native PDF | Generate Table of Contents for DITA maps and reorder page layouts

Now you can also generate the TOC in DITA maps using an advanced PDF setting of the template. You can choose to enable or disable the display of the various page layouts and also reorder their position.

### Native PDF | Add a custom bookmark in PDF output

Now you can add a custom bookmark on a particular content in your final PDF output for easy navigation. This would be added to the TOC  which is created from the topic or section titles in your DITA map. 

### Native PDF | Apply custom style on TOC entries and topic content  

AEM Guides provides the feature to apply custom styling on the TOC entries or a particular topic in the PDF output. For example, you can change color of the text in the TOC and the topic's title. You can also apply styles on the entire content within the topic.




## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

* Left panel breaks on adding a tab. (11126)
* Changes in the Web Editor html cause issues with `<dl>` and `<dlentry>`. (11024)
* Some attributes are not being treated as conditional and causing issues. (10895)
* Three levels or more nested `<indexterm>` are not nested in native PDF export. (10799)
* The content disappears in the body of a task on switching from Author to Source view. (10735)
* Review comments are misplaced in a review task. (10625)
* `<conref>` note inside a para tag is not getting displayed in the preview mode. (10559)
* Hitting backspace at the end of a list item removes the whole list. (10540)
* Screen is displayed as blank in Chrome v106 on the drag-and-drop on any element from UI ( For example, from the Conditions panel). (10524)
* Auto Indent button is missing from the toolbar in the **Source** view. (10448)
* The first character of a list item is lost sometimes when the list is being authored in the editor.( 10447)
* **Undo** or **Redo** is not working correctly on some files. (10373)
* Custom metadata is not getting retained on copy and paste action. (10367) 
* An error occurs on doing a copy (ctrl+c) and paste (ctrl+v) of content. (10304)
* Outline panel doesn't display content when switched from Author to Source mode. (10296)
* Submap does not get created when it refers to a main map in DITA Templates. (10231)
* Navigation issues occur in Web Editor after 4.0 upgrade. (10159)
* Undo option in XML Editor takes the user to the top of the page. (10091) 
* Node properties are removed after copy and paste operation of an asset. (10053)
* SVG files added to DITA topics are not displayed in preview mode of editor. (10010)
* Search results for find and replace within the Web Editor are not readable in Dark mode. (9978)
* No loader exists while creating a map from the map template. (9891)
* Conref in the topic template does not work and the hash id copied is not updated in the content copy. (9890)
* No option is displayed to browse the topics or map template inside the sub-folders of the topic or map folder. (9889)
* No option to create a new template on the subfolders of topics or maps. (9888)
* XML Editor does not update the images on topics. (9500)
* mimeType is hardcoded for DITA assets creation and update. (8979)
* A normal hyphen is inserted on selecting Non-breaking Hyphen in the **Insert Special Character** dialog. (8919) 
* Version creator name in Version History is "fmdita-serviceuser" for the files uploaded via Assets UI. (8910)
 * Edit option does not work for images while working in the Column view of Assets UI. (8758)
* DITA topic is not auto updated with changes done on **Properties** page. (8745)
* While moving elements within the topic in Web Editor, the assigned IDs on elements get overwritten by auto-assigned IDs. (7895)

### Management

* Copying a DITA map Asset (from Asset UI ) causes erroneous baselines in the copied asset. (11218)
* Warning message is not displayed on the upload of a file that is larger than the limit allowed in AEM (2 GB by default). (10817)
* Web Editor-Baseline | The behavior of the Latest column is different in the new baseline dashboard within the Web Editor. (10808)
* Translation | Translation job does not get started due to invalid /libs/fmdita/i18n/ja.json. (10543)
* Translation | An error occurs in a scoping translation project created from the translation dashboard (Human Translation). (10526)
* Translation | Post processing is blocked for the entire language folder whose assets are present in an active translation project. (10332)
* Translation| Metadata and Tags are not getting propagated to the translated copies. (4696)
* Multiple pop-ups appear for any asset if the version is changed and saved on Baseline editor. (10399)
* Session Leak occurs at com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* The video file is missing from the baseline if the parent folder contains space in the name. (10031)

### Publishing

* Topic regeneration is not working for some scenarios. (10635)
* PDF publishing fails on generating the output for a duplicate preset (of an existing preset). (10584)
* View Log button is not working in case the PDF generation fails for a preset. (10576)
* Publishlistener does not display the requested data in info logs, and it also contains some junk logs.( 10567)
* Native PDF | PDF generation fails with a Null Pointer exception. (10950)
* Native PDF | conkeyref is not getting resolved in the generated output. (10564)
* Native PDF | Issues occur with the metadata of a map that needs to be referred to in the PDF output.( 10556)
* Native PDF | Issues occur on rotating the Table header. (10555)
* Native PDF | Issues occur on removing topics that have processing role='resource-only'. (10554)
* Native PDF | Empty Keyrefs are displayed in PDF output. (10553)
* Native PDF | Nested `<indexterm>` are not nested in native PDF export. (10521)
* Native PDF | Native PDF uses inline style instead of class name for the generated tags. (10498)
* Native PDF | Nested topicref in appendices are all transformed to h1 in the temporary HTML.( 10454)
* Native PDF | Not able to hide frontmatter topics from the Table of Contents. (10355)
* Native PDF | Table frame attribute not propagated to the temporary HTML (as class). (10353)
* Native PDF | Temporary HTML files add the colsep and rowsep classes to <td> and <th> even if their value is 0 in the source DITA. (10352)
* Native PDF | Restarting page numbers in chapter layout randomly starts numbering from the end of the previous chapter. (10154)
* Native PDF | Key references for keydefs with image or external links are not getting resolved. (10063)
* Native PDF | Appendix is being displayed as a chapter in generated PDF. (9829)
* Template tab in xml editor is not getting displayed to Folder Profile admins. (10266)
* Baseline publishing fails for PDF generated using FrameMaker Publishing Server 2020. (10551)
* Application error occurs on clicking the Edit button after selecting all the presets via Output presets checkbox in Quick Generate pop-up. (10388)
* If the Output tab in Web Editor is having more presets, the presets section is not vertically scrollable, and does not display all the available presets. (9787)
* Unable to delete presets from Output workflow while publishing via Editor. (9100)
* Peer link is rendered as normal text instead of a link on the generated page. (7774)

### Known issue
Adobe has identified the following known issue for AEM Guides 4.2 release: 

* Users can perform review operations even after the review task has been completed.
