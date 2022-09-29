---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, September 2022 release
description: Latest release of Adobe Experience Manager Guides as a Cloud Service
---
# Latest release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the latest release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.9.178.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the latest release of AEM Guides as a Cloud Service.

## Steps to index the existing content 

Perform the following steps for indexing the existing content and use the new find and replace text at map level:
* Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexin`. 
(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed ||  Example :   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` 
(For example: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.


## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service September 2022 release. 

### FrameMaker and FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Not compatible | 2020 Update 4 and above |
| | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 | 
|  |  |  |  |


## New features and enhancements

AEM Guides as a Cloud Service provides many enhancements and new features in the latest release:


### Create a dynamic baseline based on labels

Now AEM Guides provides you the feature to create dynamic baselines based on labels. If you generate a baseline, download a baseline, or create a translation project using a baseline, the files are picked dynamically based on the updated labels. This feature is handy as you don’t have to modify the baseline when updating the labels. 
You can also export the snapshot of the baseline as a  CSV.

![Create baselines](assets/dynamic-baseline.png)

### Find and replace the text at map level

You can now search for files within a map that contain specific text. The searched text is highlighted in the files. You can also replace the searched word or phrase with another word or phrase within the files. 
Select the **Replace** icon to replace the current occurrence and the **Replace all in file** icon to replace all occurrences in the selected file.

![Find Replace in map](assets/map-find-replace.png)

By default, the options **Checkout file before replace** and **Create new version after replace** are selected, so a file is checked out before you replace the text, and a new version is created after the text is replaced.

### View version difference for Out of Sync files from the translation dashboard

You can now choose to translate the **Out of Sync** files based on the changes done between the two versions of a topic.  
![Translation dashboard](assets/translation-version-diff.png)
From the translation dashboard, you can easily see the differences between the last translated version and the current version of the selected file. 

![version difference dialog](assets/version-diff.png)

Based on the differences, you can decide whether you want to translate a topic or not.

### Metadata UI available for PDF Presets  

You can set the metadata from the output preset of a DITA map. You can set the Title, Author, Subject, and Keywords metadata. This metadata is mapped to the metadata in the File Properties of your output PDF. 
This metadata overrides the metadata defined at the book level. You can define the metadata specifically in each output preset and pass it on to the output PDF.  

![Metadata in Preset](assets/preset-metadata.png)


## Fixed issues

The bugs fixed in various areas are listed below:

* Web Editor | On moving elements within a topic, the assigned IDs on elements get overwritten by auto-assigned IDs. (7895)
* Track Changes | Content is lost when a new element is entered using the Enter key. (10246)
* Submap referred to the main map in dita-templates is not getting created. (10231)
* XML Editor | Copy-paste is not working in the author mode. (10309)
* Multiple version labels once selected, are not getting deselected. (9561)
* Auto navigation to the path in site browse dialog is not working like file browse. (9920)
* Outline panel doesn't display content when switched from **Author** to **Source** mode. (10319)
* Conref in a new topic created using a content in the topic template does not work. The hash id copied is not updated in the content copy. (9890)
* Web-Editor | No loader exists while creating a map from the map template. (9891)
* New Map Editor | Added bold or Italic text in the map title is not retained if we switch from **Author** to the **Layout** view. (10218)
* New Map Editor | Conditions applied on any reference cannot be removed from the Layout view. (10213)
* New Map Editor | Applying conditions references doesn't work in the Layout view like the Author view. (10198)
* New Map Editor | Move left from the context menu removes the reference if it cannot be moved left. (10219)
* New Map Editor |The icon is displayed incorrectly for the references in a map created using the Layout view. (10197)
* Repository Panel | Right-click in  the repository panel gives an application error. (10123)
* Find and Replace | Dark mode isn’t readable for search Results in the Web Editor. (9978)
* Translation | Metadata and Tags are not propagated to the translated copies. (4696)
* Copy pasting (ctrl+c/ctrl+v) content throws an error in author mode. (10304)
* PDF Template | Adding background images to any page layout displays Image Path absolute, and the images are not displayed in the output PDF. (10297)
* Native PDF | Chapter title and chapter heading is not working in PDF publishing. (9947)
* Native PDF | `xref` for a concept is not resolved correctly for a specific DITA topic. (10229)
* Native PDF | Unable to view caption text for a table in the generated PDF output. (9827)
* Native PDF | References in appendixes are not displayed as appendixes in PDF output. (10182)
* Native PDF | Frame attribute for a table is not propagated to the temp HTML (as class). (10353)
* Native PDF | temp HTML files add the colsep and rowsep classes to td and th even if their value is 0 in the source DITA. (10352)
* Native PDF |  Metadata for critdate added in page layout is not being honored. (10377)
* Native PDF |  Generation of PDF fails for specific content. (9927)
* Native PDF | Content via conkeyref is not getting displayed in the PDF output. (9836)
* Native PDF | Key references for Keydefs with images or external links are not resolved. (10063)
* Author view for a map doesn't display placeholder text for tablelist and figurelist. (10330)
* When we create a new baseline,  the already selected baseline filter is not applied. (9954)
* Video file is missing from the baseline if the parent folder name has a space character. 10031)
* Baseline creation does not pick the latest version when the user timezone is different from the server timezone. (10190)
* Control + F shortcut is not opening the browser search modal on the Assets Console after installing AEM Guides 4.1 on AEM 6.5.12. (10189)


## Known issues

Adobe has identified the following known issues for AEM Guides as a Cloud Service September 2022 release.


* Dynamic baseline is not integrated with knowledge base publishing. 

* Translation | Version difference icon appears for the source content due to any change in the target content. 
