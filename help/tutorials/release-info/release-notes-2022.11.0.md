---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, November 2022 release
description: Latest release of Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
---
# Latest release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the latest release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.11.198.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the latest release of AEM Guides as a Cloud Service.

## Steps to index the existing content (Only if you are on a version prior to September release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

* Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexin`.
(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed || Example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(For example: http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service November 2022 release. 

### FrameMaker and FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Not compatible | 2020 Update 4 and above |
| | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 | 
|  |  |  |  |


## New features and enhancements

AEM Guides as a Cloud Service provides enhancements and new features in the latest release:


### Delete files from the repository panel

Now you can easily delete files (single file at a time) from the **Options** menu of the selected file from repository panel.
<img src="assets/repository-delete-file.png" alt="Delete from repository" width=500>

A confirmation prompt is displayed before deleting the file. If the file is not referenced from any other file, it is deleted, and a success message is displayed.

If the selected file is checked out, you cannot delete it, and an error message is displayed. If the selected file is added to a favorites collection or is referenced from any other file, AEM guides checks for your confirmation and gives you the option to forcefully delete it. If you delete a referenced topic and you have opened the file containing references for edit, it will show the broken link for the referenced file.

**Note**: You can also delete the selected file using the Delete key of the keyboard.


### Purging selected versions of files  

As you create and maintain your content, many versions might get created for your DITA files in your repository. AEM Guides allows you to purge older versions of your DITA files from the repository and free up disk space. 

<img  src="assets/preview-purge-report.png" alt="Preview purge report" width=500>


AEM Guides does not delete the first version of the file or a version that is included in a baseline, or has a label applied to it. Purge operation doesn't even delete files that are included in a translation or a review workflow. You can choose the number of versions to retain and also decide to delete the files which are older than the defined number of days.

Before starting the purge operation, you can preview the report to see the versions that will be purged. You can then decide to start or cancel the purge operation. 

<img  src="assets/download-purge-report.png" alt="PDownload purge report" width=500>

Once the purge operation is complete, you can check the purge report to see the purged files.

### Manage Global and Folder Profile output presets 

AEM Guides provide you the feature to create and manage output presets for the Global and Folder Profiles. Then you can easily use these output presets to generate output for all maps that are related to that Global or Folder profile.

<img  src="assets/add-global-output-preset.png" alt="Add global profile" width=400>

**Note** Only folder level administrative users can create Global and Folder Profile presets. 

These global presets appear under the **Output** tab of all related maps. You can use them to  generate the output for all the related maps. You can select the preset as default PDF preset to generate the PDF output. You can also **Edit**, **Rename**, **Duplicate**, or **Delete** an existing output preset from the **Options** menu.

### Version Label column added to the translation dashboard

In the translation dashboard, you can also see the Version Label column. This displays the Label for the selected version of the source file. This can help you select all files with a specific label and translate them in one go. 

<img  src="assets/send-translation.png" alt="send for translation" width=600>


### Native PDF | PDF with change bar showing the difference between document versions   

Now you can create a PDF that shows the differences in content between two versions using change bar. You can choose to compare the current version with a baseline of the previous version or compare between the two selected baseline versions. 

<img  src="assets/pdf-change-version.png" alt="spdf-change-version" width=600>

A change bar appears in the PDF to indicate the modified, inserted, or deleted content. You also have the options to do the following:
* Show the inserted content in green color and underlined
* Show the deleted content in red color and marked with a strikethrough

### Native PDF | Variable support for Output Path and PDF File name

Now you can also use the following out-of-box variables to define the Output Path and PDF File. You can use a single or a combination of variables to define these options:
* `${map_filename}`
* `${map_title}`
* `${preset_name}` 
* `${language_code}` 
* `${map_parentpath}` (Only for Output Path)
* `${path_after_langfolder}` (Only for Output Path)


### Native PDF | Generate Table of Contents for DITA maps and reorder page layouts

Now you can also generate the TOC in DITA maps using an advanced PDF setting of the template. You can choose to enable or disable the display of the various page layouts and also reorder their position. 

## Fixed issues

The bugs fixed in various areas are listed below:

* Native PDF | `conkeyref` does not get resolved in the generated PDF output. (10564)
* Native PDF | Issues occur on accessing metadata of a map in the PDF output. (10556)
* Native PDF | Inline style are used for generating tags instead of class name.  (10498)
* Web Editor loads blank page intermittently. (10678)
* PDF publishing fails if we create a preset via duplicating an existing preset. (10584)
* **View Log** button is not working when the PDF generation fails for a preset. (10576)
* Note inside a para tag which is a conref is not getting displayed in the preview. (10559)
* Hitting backspace at the end of a list item removes the whole list. (10540)
* On using a native PDF export the nested `<indexterm>` are not nested in the index. (10521)
* **Auto-Indent** button in the toolbar is missing in the  Source View. (10448)
* First character of a list item is lost while the list is being authored in the editor. (10447)
* Multiple pop ups appear if any DITA asset version is changed and saved in baseline editing window. (10399)
* Application error occurs on clicking **Edit** button after selecting all the Output presets from the Quick Generate panel. (10388)
* Custom metadata for DITA topic is not retained when a copy paste action is performed from the Assets UI. (10367)
* Post processing is blocked for entire language folder whose assets are present in an active translation project. (10332)
* Template tab in XML Editor is not visible to folder profile administrators. (10266)
* Navigation issues occur in Web Editor after 4.0 upgrade. (10159)
* SVG files are not getting displayed in Preview mode. (10010)
* If Editor's Output tab contains more presets, the presets section cannot be scrolled, and all the presets are not displayed. (9787)
* **Edit** and **Annotate** options for an image are not working correctly in the column view. (8758)
* Peer link is not resolved and appears as a normal text in the generated output. (7774)
