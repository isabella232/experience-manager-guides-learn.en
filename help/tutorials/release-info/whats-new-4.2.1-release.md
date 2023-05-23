---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.2.1 release
description: Learn the new and enhanced features in 4.2.1 releases of Adobe Experience Manager Guides
---
# What's new in 4.2.1 release of Adobe Experience Manager Guides (May 2023)

This article covers the new and enhanced features in version 4.2.1 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-4.2.1.md) article.

## Navigate from the Web Editor to the AEM homepage 

Now you can easily navigate from the Web Editor to the AEM Navigation page. 

![](assets/web-editor-launch-page.png){width="800" align="left"}

*  Click the **Guides** icon (![](assets/aem-guides-icon.png) ), to go back to the AEM Navigation page. 


For more details, see [AEM Navigation page](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ) 

## Advanced metadata support in PDF publishing

AEM Guides now provides advanced support for the metadata which is mapped to the metadata in your PDF output. The metadata options include information about the document and its contents, such as the author's name, document title, keywords, copyright information, and other data fields.

<img src="assets/pdf-metadata.png" alt=" native pdf metadata">

You can import a XMP file and AEM Guides can pick the information from the file. You also have the option to provide the metadata names and values using the dropdown. You can also add custom metadata by typing directly in the name field.

For more details, see **Metadata** feature description in [Create a PDF output preset](../web-editor/native-pdf-web-editor.md).

### Enhanced Outline View panel

AEM Guides provides an improved Outline View panel in which you get the hierarchical view of the elements used in the document.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native pdf metadata">

The Outline View provides the following enhancements:

* View Options dropdown is displayed on top of the Outline View panel. If an element has an ID, attribute, and text, you can select them from the dropdown to display them along with the element. The attributes which can be displayed in the Outline View panel are determined by the Display Attributes settings that have been configured by your administrator within the **Editor Settings**.

* Using the search feature, you can  you can search for an element by its name, id, text or attribute value. 

For more details, see the Outline view feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Generate the Multimedia report from the Web Editor

AEM Guides provides the feature to generate the reports for your technical documents.  You can use this feature to view the topic list and manage the metadata of your documents. Now you can also see the multimedia used in all references for the current map from the **Reports** tab in the Web Editor. 

You can generate the multimedia report which contains detailed information about the multimedia used in your references within the current map. You have the flexibility to filter and sort the multimedia files listed in the report.
You can also generate the CSV to download the current snapshot of the multimedia used in the DITA map.

<img  src="assets/web-editor-reports-multimedia.png" alt="multimedia report" width=600>

For more details, see the Generate a multimedia report feature description in the [DITA map report from the Web Editor](../user-guide/reports-web-editor.md) section.

## Native PDF | Change bar to indicate changed topics in Table of Contents

AEM Guides  now allows you to quickly identify the changed topics in the TOC of the PDF output.  It shows a change bar on the left of the changed topics in the TOC. You can click on the topic in the TOC and view the detailed changes.

<img src="assets/change-marker-toc.png" alt="Change marker in TOC " width=500> 

For more details, see [Work with custom change bars styles](../native-pdf/change-bar-style.md).



## Native PDF | Style the page marker in footnote component

Now you can style the page marker in the foot notes. For example, you can add brackets or change their color. These styles help the users easily identify the page markers in the document.

For more details, see [Use custom styles in footnotes](../native-pdf/footnote-number-style.md).

## Open and play video or audio files in the Web Editor

AEM Guides now provides the feature to open and play the audio or video files in the Web Editor. You can change the volume or the view of the video. In the shortcut menu, you  also have the options to **Download**, change **Play back Speed**, or view **Picture in Picture**.

<img  src ="assets/video-web-editor.png" alt="play video" width=600>

For more details, see the Repository View feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.
