---
title: Release Notes | Adobe Experience Manager Guides 4.2 release
description: Learn about the bug fixes and how to upgrade to  4.2 releases of Adobe Experience Manager Guides
---
# 4.2 release of Adobe Experience Manager Guides (February 2023)

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version 4.2 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more information about the new features and enhancements, see [What's new in 4.2 release of Adobe Experience Manager Guides](whats-new-4.2-release.md).

## Upgrade to 4.2 release of AEM Guides

You can easily upgrade your current version of AEM Guides to version 4.2. Before you proceed with upgrading to version 4.2 of AEM Guides, you must consider the following points:
* If you are using version 4.0, 4.1, or 4.1.x, then you can directly upgrade to version 4.2.
* If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
* If you are on a version prior to 3.8.5, refer to the *Upgrade AEM Guides* section in the product-specific installation guide.

>[!NOTE]
>
>You must install AEM service pack before upgrading AEM Guides version.

For details, see [Upgrade instructions](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

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

## Known issue

Adobe has identified the following known issue for AEM Guides 4.2 release: 

* Users can perform review operations even after the review task has been completed.
