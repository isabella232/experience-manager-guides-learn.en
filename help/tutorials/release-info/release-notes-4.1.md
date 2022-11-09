---
title: Release Notes | Adobe Experience Manager Guides 4.1 release
description: Latest release of Adobe Experience Manager Guides
exl-id: c70b3bbc-3332-4626-bc30-641034f8fd06
---
# 4.1.x release of Adobe Experience Manager Guides

This release notes covers the upgrade instructions, new features, and enhancements in version 4.1.x of Adobe Experience Manager Guides (later referred as *AEM Guides*).

## Upgrade to the latest release

You can easily upgrade your current version of AEM Guides to version 4.1.2. Before you proceed with upgrading to version 4.1.2 of AEM Guides, you must consider the following points:
* If you are using version 4.1 or 4.1.x, then you can directly upgrade to version 4.1.2.
* If you are using version 4.0.x, then you need to upgrade to version 4.1 or 4.1.x before upgrading to 4.1.2.
* If you are using version 3.8.5, then you need to upgrade to version 4.0.x before upgrading to 4.1.
* If you are on a version prior to 3.8.5, refer to the upgrade section in the product-specific installation guide.

For details, see [Upgrade instructions](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4.1.2 | Release notes

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.1.2 release. 

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 13, 12, 11, or 10

**UUID**
Version 6.5 Service Pack 13, 12, 11, or 10

For more details, see the Technical requirements section in the Install and configure Adobe Experience Manager Guides guide. 


### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
|4.1.2 (Non-UUID)| 2020.2 or higher* | 2019 | 2020.3 or higher | 2019.8 (latest update) |
| 4.1.2 (UUID) | 2020.2 or higher* | Not compatible | 2020.4 or higher | Not compatible |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.1.2 (Non-UUID)|  2.0 | 2.0 |  1.6 | 1.6  |
| 4.1.2 (UUID) | 2.7 | 2.7  |2.3 | 2.3  |
|  |  |   |  


## Fixed issues

The bugs fixed in various areas are listed below:

* On selecting all folder profiles, an invisible folder profile (which is incorrect) appears. (10393)
* Baseline creation does not pick the latest version, when the user's timezone is different from the server timezone. (10336) 
* Control+F shortcut is not opening the browser search modal on the Assets Console after the installation of AEM Guides 4.1. (10339)
* Baseline creation error occurs for the topic which has the reference to a folder. (10383)
* Output presets tab is showcasing a blank screen intermittently and in some cases non-editable presets are getting displayed. (10390)
* Keyspace management is leading to exceptions and errors. (10449)

### Known issues with workaround

* Baseline exported during translation does not load in the baseline tab of editor.

  **Workaround**: Use the baseline tab of DITA map dashboard.

## 4.1 | Release Notes

This release notes covers the upgrade instructions, new features, and enhancements in version 4.1.x of Adobe Experience Manager Guides (later referred as *AEM Guides*).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.1 release. 

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 13, 12, 10, or 11

**UUID**
Version 6.5 Service Pack 13, 12, 10, or 11

For more details, see the Technical requirements section in the Install and configure Adobe Experience Manager Guides guide. 




### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
|4.1 (Non-UUID)| 2020.2 or higher* | 2019 | 2020.3 or higher | 2019.8 (latest update) |
| 4.1 (UUID) | 2020.2 or higher* | Not compatible | 2020.4 or higher | Not compatible |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.1 (Non-UUID)| 2.0 | 2.0 |  1.6 | 1.6 |
| 4.1 (UUID) | 2.7 | 2.7 |2.3 | 2.3 |
|  |  |  |  


## New features and enhancements

AEM Guides provides many enhancements and new features in the 4.1 release:

### Native PDF publishing

Support for creating a native PDF has also been added in the 4.1 release of AEM Guides. A new publishing engine has been introduced with the following features:
* Create a CSS template
* Create different page templates
* Design PDF templates comprising CSS and page templates
* Publish map and topic content in PDF format 

### Enhanced Web Editor

* **Improved key resolution**

A DITA content key reference inserts a part of content from one topic into another. It uses a key to locate the content. The key references associated with a DITA topic need to be resolved. The selected root map takes the highest precedence to resolve key references. 

![user preferences dialog](assets/user-preferences.png)

Now the key references are resolved on the basis of the root map set in the following order of priority: 

1. User Preferences
2. Map View panel 
3. Folder Profile

For more details, see *Resolve key references* section in the Using Adobe Experience Manager Guides guide.

* **Add a custom panel in the left panel**

Now you can add a custom panel within the left panel of the Web Editor. You can use a custom panel for various purposes like providing help or doing the testing for a project. If a custom panel has been configured, then it also appears in the list of panels within the **Editor Settings**. You can toggle the switch to show or hide the custom panel.

* **Ability to change the document state of topics in a DITA map**

Now you can easily change the document state of selected topics within a DITA map. You can also open and edit the properties of selected topics in a DITA map from the **More Options** menu at the bottom of the Map View panel.

![selected topic properties](assets/map-view-properties.png)

* **Version information displayed in the Preview mode**

The Web Editor helps you in managing your versions. Now you can also see the version of the active topic or DITA map in the top right corner of the topic's file tab in the Preview mode of a topic.

![preview version](assets/preview-version.png)


* **Improved Web Editor refresh behavior**

The following  enhancements are now available with the browser refresh operation in the Web Editor:

* Now you get the support to refresh the browser while you edit your 
content in the Web Editor. If you hit the browser refresh icon while one or more files with
unsaved changes are opened for editing, you are prompted to save your files or cancel the refresh action. 

* Even on refreshing the browser, the views of the left panel and the right panel are retained.  

* The active topic or DITA map is reopened in the content editing area.

* **Create maps based on customized templates** 

Now you get the powerful feature to create customized map templates. You can use them to create DITA maps along with the topic templates and map templates referenced in the map template. 

![dita templates](assets/dita-templates.png)

You can also refer to other map templates and topic templates from the customized map template. The referred map templates can refer to various map templates, topic templates, topics, maps, images, videos, and other assets.

![create dita templates](assets/create-dita-template.png)

The customized map template can help you very easily replicate the map templates and the entire referred folder structure. These customized templates are especially useful to create and recreate multiple maps which have recursive structures and references. 

* **Schematron support**
“Schematron” refers to a rule-based validation language used to define tests for an XML file. Using a Schematron file you can define certain rules and then validate them for a DITA topic or a map. Web editor supports Schematron files. You can import the Schematron files and also edit them in Web Editor. The Schematron support in the Web Editor helps you in validating the files against a set of rules and maintaining consistency and correctness across the topics. 

![validate schematron](assets/schematron-validate.png)

* **Improved dialog on file close**

AEM Guides prompts you to save your changes and unlock your locked files when you try to close a file opened in the Web Editor. The prompts are displayed based on the **Ask for check-in on close** and **Ask for new version on close** settings configured by your administrator.

Based on the configuration, you get the option to save the changes and create a new version of your document. Or, you can also check in the file and save the changes to the current version.  

![File close](assets/file-close-save-changes-unlock.png)

For more details, see *File close and save scenarios* section in the Using Adobe Experience Manager Guides guide.* The **Insert Keyword** feature has been improved. You can now more easily find a Keyword to be inserted as the keywords are listed in alphabetical order. You can also search keyword(s) by typing a search string in the Search box. 

![insert keyword](assets/insert-keyword.png)

* **Support for Markdown documents**
Markdown is a lightweight markup language that can help you add formatting elements to plain text documents. The Web Editor allows you to use Markdown documents (.md) along with your DITA documents. You can easily author and preview a Markdown document in the Web Editor and also add it in your map file through DITA map editor.  For more details, see *Author Markdown documents from the Web Editor* section in  Using Adobe Experience Manager Guides guide.

![support markdown](assets/create-markdown-dita-topic.png)

* **Ability to configure a default tags view**
If a user enables the Tags View from the Web Editor, it remains enabled even across the sessions.  This means that you don't have to enable the Tags View again to access it later. Your administrator can configure the default state for the Tags View in the Web Editor. The default value for Tags View for a new user's session is determined by the tagsView property in the ui_config.json file.

* Now in the Repository View files are loaded in batches. All the files present in the main or `/content/dam folder` are listed. But from the next level or the secondary folder 75 files are loaded at a time. This batch loading is efficient, and you can access the files faster in comparison to loading all the files existing in a folder.

![load more files](assets/load-more-files.png)

### New Baseline dashboard

AEM Guides 4.1 release provides the Baseline feature integrated inside the Web Editor. You can now create baselines from the Web Editor and use them to publish or translate topics of different versions.

**Note**: For upgraded system, please update the latest **ui_config.json** for Folder Profile.

Use this feature to create a baseline with a specific version of the topics available on a specific date and time. Also, you get the API support to create or update a baseline with a label defined for a version of topics. 

![baseline manage tab](assets/baseline-manage.png)

You can search the files based on filenames, or file location. You can also filter the topics to be displayed in the baseline editing window and sort them based on specific columns. 

![baseline manage tab](assets/baseline-filter.png)

The performance for the baseline creation process has been further improved. The process to create baselines is asynchronous, so you can continue editing other files in the Web Editor while the baseline is being created. For more details, see *Create and manage baselines from the Web Editor* in the Using Adobe Experience Manager Guides guide. 

Note: The Baseline tab on the map dashboard is hidden by default. Your administrator can enable the Baseline tab on the map dashboard.

* The baseline parameter in the APIs to Download Map now uses the title of the baseline to retrieve the versioned content.

### Improved Translation Process

* **Ability to create a scoping translation project**
If you need to create only the scope for a project to be translated, you can select **Create a new scoping translation project**. This will not send the copies for translation and the original translation status of the files is maintained. 
 
![scoping translation project](assets/scoping-translation-project.png)

* The **Languages** list displays the language folders along with their language codes. For example, French (fr) and German (de).

![translation languaged](assets/translation-languages.png)

For more details on translation, see *Translate documents from the Web Editor* section in  Using Adobe Experience Manager Guides guide.


### Enhanced Publishing

* You can also access the **Publish Dashboard** from the Outputs tab while you generate output from the map dashboard. A list of all active publishing tasks is available in the Publish Dashboard. 

![queued outputs](assets/queued-output.png)

* From the map dashboard you can select multiple DITAVAL files to generate conditionalized content. You can maintain the file order by adding or deleting files. You can also hover over the file name to see the path in the AEM repository where the file is stored. 

* Baselines have been honored for the metadata of AEM site output. You can also process the properties of a baseline version as metadata. If no baseline is defined, then the properties of the latest version are processed as metadata.

* The **File Name** and **DITA-OT Command Line Arguments** options have been added for HTML5, EPUB, and Custom output presets. Now you can specify the file name with which you want to save the output. You can also specify the additional arguments that you want DITA-OT to process while generating output.

### Map dashboard

When you select to download the DITA map, the request is queued, and you receive a notification once the map is ready to download. You can choose to download the map file immediately or download it later from the link provided in the AEM notification Inbox. 

![Map download](assets/download-map-prompt.png)

### Other Feature Enhancements

* AEM Guides now supports Oxygen XML Author version 24.1.
* The baseline parameter in the APIs to Download Map now uses the title of the baseline to retrieve the versioned content.

### Deprecated Feature

AEM Guides no longer supports the generation of DITA output format for FrameMaker documents. This DITA option has also been removed from the Output Presets of the Map dashboard.

## Fixed issues

The bugs fixed in various areas are listed below:

* Authoring support not available as an alternate for file path-based referencing for publishing. (8076) 
* DITA Add on package prevents the DAM duplicate asset detection. (8417)
* After check-in of a document from Oxygen to AEM, Japanese content in the document gets replaced by question marks (???). (9124)
* Refresh checked out files is not working on logging with Web authentication in Oxygen. (9179)
* File is not checked out when opened in Oxygen. (9192)
* After check-in of a document from Oxygen to AEM, Japanese content in the document gets replaced by question marks (???). (9276)
* Web Authentication not working in Oxygen. (9296)
* Reupload fails in Oxygen when the file(s) already exist in AEM at the same location. (9328)
* Option not available to forcefully sync content between AEM and the local system. (9439)
* ID is not automatically generated for element added using **Insert Reusable Content** dialog from secondary tool bar. (5826) 
* No confirmation dialog is displayed on uploading an image with the same name as an existing file, via the editor. (6011)
* A non-breaking space not available in the character pallet. (7523)
* The element list (Alt+Enter) appears grayed out in Dark/Darkest theme. (7913)
* Version is not updated on saving the revision of a topic from map panel toolbar. (8228)
* xref cannot be inserted even at valid locations. (8354)
* 'getversionlabels' operation has limitations and doesn’t give expected performance. (8513) 
* Issues occur with confirmation dialog on closing a locked or edited file which is not currently opened in editor. (8692)
* Error occurs on adding a user as an administrator in the folder profile when the user ID is numeric. (8908)
* Translation panel is visible even on opening the DITA map in the Map Editor. (9053)
* Language code is not displayed with the language in the Translation panel. (9108)
* Translation and Baseline tabs are visible for some time on the Map dashboard. (9146)
* When the translation is done, an additional version is created for the translated asset. (9310) 
* Approved translation does not integrate to the target language when the target language code contains five characters like `fr_ca`. (9357)
* Translated content is broken when the target language code created is mentioned as `fr-fr, `, `en-us`. (9527) 
* On loading a DITA map that is outside the language folder, an exception is logged at the backend.(9543)
* Unable to create DITA file using the custom DITA template from the editor. (7262)
* The DITA map is lost on publishing a UUID DITA map via FMPS. (7278) 
* AEM Guides does not copy the non-unique properties of an asset when an asset is copied and pasted. (8241) 
* DITA map filename not getting converted to lower case on creation. (8383)
* Review task description does not appear in the email notification being sent when a new review task is being assigned. (8507)
* Download map API | Temporary folders not getting cleaned up in case download process errors out. (8523)
* `columnpreview.jsp` is dependent on SP.  (8543)
* Output jobs with status like ‘Waiting’ or ‘Executing’ do not get cleaned up in the Publish Dashboard.  (8569)
* Default icon picked on generating a report using the Generate button, even when the icon property is defined. (8573)
* Issues occur in review process while upgrading from 3.8.X to 4.0. (8788)
* In the Review panel of the Web Editor, if a username is long, the icons to accept/reject are not displayed clearly. (8793)
* Reference tree breaks after removing a topic and performing a move operation. (8804) 
* Custom DTD defined by the user does not take precedence over standard DITA DTD embedded in DITA-OT. (9104)
* Position of highlighting is incorrect in Side-By-Side view. (9305)
* Use-by-reference footnote doesn't scroll to the footnote section in AEM site output. (9061) 
* Order of footnotes is incorrect in the AEM Site output. (9327)
* Newly created DITA assets are always checked out by another user. (9387)
* Error always gets logged on the creation of new content. (9388)
* The third screen in the review task creation process does not show the list of glossaries. (4558)
* Incorrect UUID references assigned when uploading multiple files from FrameMaker/Oxygen Connector. (8269)
* Email notification is not being sent when a review task is being re-assigned in the Inbox. (8376)
* The second administrator user cannot be added as the first administrator user to a folder. (8430)
* **Apply Labels** dialog on the Baseline tab does not display labels in dropdown. (8455)
* On using baseline publishing with image as conref in the topic, the image is not published in the output. (8564)
* Output purging feature fails if large number of leftover output history nodes are present. (8568)
* Within the version history panel, the current version section shows incorrect timestamp and modified by information. (8765)
* Baseline not updated on the basis of the label defined. (8799)
* Error occurs when files whose parent folder has special characters in the filename, are opened in Oxygen (using the **Edit in Oxygen** button). (8918)
* Uploading files from Oxygen to AEM fails. (9157)
* Download map with baseline not working if the content is moved to some other folder. (9331)
* Oxygen checks out an incorrect version of a topic after a version revert in AEM. (9411)
* Search in Repository panel and topicref browse dialog freezes the screen when the content is large. (9432)
* If the setting **Create New Version for Uploaded File** is ON, a new version is created on reverting and saving on any frozen node. (9473)
* Incorrect timestamp differences are displayed in Assets UI on reverting a file version. (9480)
* Files are checked out automatically on reverting to any version. (9482)
* Lock icon is displayed in the repository view even when the file is checked in from the editor.  (5756)
* Unable to add frontmatter, backmatter elements in a bookmap using the Author view of the Web Editor. (7652)
* The Preview mode does not support `deliveryTarget` conditional processing attribute in DITA. (7685)
* On opening a glossary topic in the XML editor, AEM forces to save it even if it hasn’t been modified. (8105)
* Insert references dialog opens on adding subjectref to a map using UI. (8212)
* Reuse content panel crashes on searching special characters `[` or `*` .(8279)
* On authoring Glossentry, the Web Editor shows the content as a Note. (8384)
* XML Editor removes newline in codeblock. (8522)
* Switching between source and author mode marks the topic as dirty and requires the content to be saved again.(8524)
* Unable to close an unlocked topic. (8545)
* No option exists to choose the Knowledge Base path in article-based publishing presets. (8636)
* Attributes are  missing on adding a chapter into bookmap using Drag-and-drop from the Favorites view. (8746)
* Insert Keyword dialog doesn’t have the search ability and keywords are not listed in sorted order. (9094)
* Performing a search in XML Editor causes the page to freeze. (9452) 
* Sites are missing in AEM presets under the Output tab. (9567)
* SVG images that do not render correctly in author modes of XML Editor. (9426)
* Baseline is not being honored while publishing via salesforce. (8953) 
* Ability to clear rootmap from the user preferences settings is not present. (8534)
