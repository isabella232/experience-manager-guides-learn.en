---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides 4.3.1 release
description: Learn about the bug fixes and how to upgrade to  4.3.1 releases of Adobe Experience Manager Guides
---
# 4.3.1 release of Adobe Experience Manager Guides (October 2023)

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version 4.3.1 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more information about the new features and enhancements, see [What's new in 4.3.1 release of Adobe Experience Manager Guides](./whats-new-4.3.1-release.md).

## Upgrade to 4.3.1 release of AEM Guides


You can easily upgrade your current version of AEM Guides to version 4.3.1. Before you proceed with upgrading to version 4.3.1 of AEM Guides, you must consider the following points:
You can upgrade your current version of AEM Guides to version 4.3.1

- If you are using version 4.2 or 4.2.x then you can directly upgrade to version 4.3.1.
- If you are using version 4.1 or 4.1.x then you need to upgrade to version 4.2 or 4.2.x before upgrading to version 4.3.1.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.1.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade AEM Guides section in the product-specific installation guide.



>[!NOTE]
>
>You must install AEM service pack before upgrading AEM Guides version.

For details, see [Upgrade instructions](../install-guide/upgrade-xml-documentation.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.3.1 release. 

### Adobe Experience Manager

**4.3.1 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15, or 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, or 14

For more details, see the *Technical requirements* section in the Install and configure Adobe Experience Manager Guides guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.3.1 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
| 4.3.1 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.3.1 (Non-UUID)|  2.3-regular-5| 2.3-regular-5 |  1.6 | 1.6  |
| 4.3.1 (UUID) | 3.0-uuid-4|3.0-uuid-3 |2.3 | 2.3  |
|  |  |   |  

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- Afternoon hours are not set in the **Date** for the creation of baselines. (12712)
- Not able to paste the JSON code in the `<codeblock>` element of the Web Editor. (12326)
- Unsaved version changes and the indicators for them are not displayed for large files. (11784)
- While editing in the Korean language, the first character changes to the default. (10049) 

- The prefix is duplicated in the preview mode of the Web Editor. (13133)
- `Choicetable` rows are not displayed or cannot be selected. (12616)
- The Web Editor throws validation errors in specific scenarios when creating a topic using a custom schema. (12576)
- The ditaval topic template references don’t create a copy in the content folder when creating a map from the map template. (12150)

- The search box in DITA maps does not have a close button. (11867)
- On saving long files in the Web Editor, `DirtyChecker` throws an exception with a long stack trace and fills the log files. (11860)
- Creating DITA topics requires Delete permission on the corresponding folder node, although the map can be created with Write permission. (11706)
- Web Editor shows an incorrect title when a slash is present. (10949)

- If the title of a topic contains a slash "/", the tab in the editor only shows the letters coming after that. (13455)
- The image preview doesn’t disappear after displaying the preview in the Editor. (13454)
- Some of the existing version or their labels are not displayed in the Version History after the upgrade to 4.x. (13247)
- The Version History panel in Assets UI shows an incorrect timestamp for the **Current** field. (12624)
- Topic with conref title is not resolved in Repository View or Map View.(13304)


### Publishing

- Native PDF | The order of the topics isn't fixed when the PDF output is generated. (13157)
- Native PDF| No default style tag is available for `<p>`element. (12559)
- Native PDF | Inline styles applied to the content region are not applied to the topics in front matter and back matter. (13510)
- The `DeliveryTarget` attribute isn't propagated on generating the AEM Site output.  (13132)
- The **Publish** workflow gets stuck while generating AEM Site output for content with certain errors. (12000)

- Native PDF | Including multiple xrefs extends the text beyond the column width. (13004)
- Native PDF | When the topic and title have the same ID, it leads to a malformed generation of the PDF output. (12644)
- Native PDF | On adding an outputclass to a parent `<topicref>` element in a DITA map and applying custom style to the outputclass, the styling is applied to elements within the topic body, including section titles. (12166)
- Incremental publishing doesn’t work if a DITA map has multiple ditavalrefs. (12117)
- AEM Site | On creating a map with keydef pointing to a topic as a variable and adding processing-role=resource-only creates some unexpected pages. (12099)
- If any assets from AEM’s DAM are used in any output other than the AEM site, then the metadata "jcr:createdBy" does not reflect the publisher’s name or the name of the user who last modified the DITA map or topic. (12090)
- AEM Sites | DITA map with topichead in the navtitle (with non-supported characters) leads to bad page URLs. (11978)
- Native PDF | Issues occur in support of topichead / topicmeta / navtitle in Frontmatter and Backmatter. (11969)
- Native PDF | Generating PDFs for large documents is time-consuming. (11955)
- Native PDF | Renaming a preset throws a NullPointerException while generating a PDF output. (11889)
- The `<conref>` content isn’t shown in the PDF output. (11131)
- An extra space gets added inside the `<div>` elements on toggling between the Author and Source view in the page layout editor. (10750)
- The content replicated on the AEM Cloud manager isn’t visible on the Publish instance. (9564)


### Management

- Version History doesn’t show even if the `dc:format` property isn't present for an asset. (10463)
- Content reference is broken copy-pasting DITA files when the topic id isn’t the same as GUID. (12614)
- In dynamic baselines, the list of labels isn’t pulled from the direct references of the working copy of a DITA map. (11917)
-  Baseline shows the incorrect number of files on the Map Dashboard when using the Browse all topics functionality. (13265)
-  In the Web Editor, the baseline shows the title for the previous version instead of the selected version of the DITA file. (13444)

### Review

- The Review on a topic shows incorrect comments. (13453)
- The Close button on the Review page in the Experience Manager Guides takes the users to the AEM Homepage. (13535)
- Attachments are not displayed on the editor's right panel for an In-review topic. (13011)



### Translation

- The baseline exported from the **Translation** dashboard fails and doesn’t open in the target language. (13466)

- New translation projects are created instead of adding new jobs to the selected existing translation projects.  (10214)
- The title of the translated file is displayed in place of the title of the source file. (11630)
- Auto approve isn't working sometimes, and exceptions occur if an incorrect value is set on Translation Status. (13607)
- The baseline exported from the Translation dashboard fails and doesn't open in the target language. (12993)
- Some files are missing while using Baselines in translation. (13021)