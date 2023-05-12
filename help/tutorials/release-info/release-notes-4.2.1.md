---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides 4.2.1 release
description: Learn about the bug fixes and how to upgrade to  4.2.1 releases of Adobe Experience Manager Guides
---
# 4.2.1 release of Adobe Experience Manager Guides (May 2023)

This release note covers the upgrade instructions, compatibility matrix, and issues fixed version 4.2.1 release of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more information about the new features and enhancements, see [What's new in 4.2.1 release of Adobe Experience Manager Guides](whats-new-4.2.1-release.md).

## Upgrade to 4.2.1 release of AEM Guides


You can easily upgrade your current version of AEM Guides to version 4.2.1 Before you proceed with upgrading to version 4.2.1 of AEM Guides, you must consider the following points:
You can upgrade your current version of AEM Guides to version 4.2.1
*   If you are using version 4.1, 4.1.x, or 4.2, then you can directly upgrade to version 4.2.1.
*   If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.2.1.
*   If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
*   If you are on a version prior to 3.8.5, refer to the Upgrade AEM Guides section in the product-specific installation guide.

>[!NOTE]
>
>You must install AEM service pack before upgrading AEM Guides version.

For details, see [Upgrade instructions](../install-guide/upgrade-xml-documentation.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.2. 1 release. 

### Adobe Experience Manager

**Non-UUID**
Version 6.5 Service Pack 15, 14, 13, or 12

**UUID**
Version 6.5 Service Pack 15, 14, 13, or 12

For more details, see the *Technical requirements* section in the Install and configure Adobe Experience Manager Guides guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.2.1 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
| 4.2.1 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.2.1 (Non-UUID)|  2.1-regular-4 | 2.1-regular-4 |  1.6 | 1.6  |
| 4.2.1 (UUID) | 2.8-uuid-8 | 2.8-uuid-8  |2.3 | 2.3  |
|  |  |   |  

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

* Close button in Web Editor does not lead to AEM Navigation page. (11948)
* Sometimes application error occurs on clicking on a DITA map. (11842)
* Issue occurs on moving (drag and drop) in place of an existing list item with Track Changes on. (11570)
* Issue occurs on moving (drag and drop) as a new list item with Track Changes on. (11569)
* Indent or outdent list items does not work as expected with Track Changes on. (11568)
* Adding content on a line with Track Changes on, and then turning off Track Changes does not actually turn it off. (11567)
* Difficulty in dragging and dropping a list-item, text is moved in place of the list-item. (11566)
* On authoring in the element displayed in green (Track Changes,) the new content is displayed as track change even though the track change is disabled. (7021)
* The browser (Web Editor) freezes on loading content with custom schema. (11211)
* Native PDF | On creating an output preset with “Add to Folder Profile” option, PDF generation fails with a Null Pointer exception. (10950)
* Native PDF | Image tag adds display-inline attribute to all the images. (10653)
* Insertion for audio and video multimedia files fails in the YouTube format under the **Insert Multimedia** icon. (11320)
* Validation error occurs when a map is created using the template which has a specialized title element. (11212)
* Web Editor | Non-breaking space is added in XML Editor while editing a topic. (11211)

### Management

* Reports tab in the Web Editor UI doesn't display the topic list of old DITA maps created before the 4.2 upgrade. (11708)

* The Upload files button functionality in the Assets UI break in 4.2 release. (11633)


### Publishing

* Native PDF | Publishing content that has an output class with brackets() leads to a publishing freeze. (11936)
* JSON output | Map metadata having property value as `"value in spaces and double quotes"` leads to a publishing error. (11933)
* Issue occurs in AEM Site search (doesn’t work beyond 2-3 level nodes). (11352)
* Web Editor | Output path and template cannot be selected in the AEM Preset. (11530) 
* On upgrading from 4.1.x to 4.2 release the Native PDF engine does not work and throws NullPointerException even for the supported OS.(11526)
* Download PDF process is not working appropriately in the Web Editor. (11496)
* Native PDF | Draft comments are hidden by default in the generated output. (10560)
* Native PDF | navtitle is not honored for topichead. (10509)
* Native PDF | Adding `xref` to an Image does not render the image on the generated PDF. (11346)

### Translation

* With 4.2 upgrade, all the translation content shows Out of Sync or Missing Copy. (11834)

### Review

* Completed review does not open in read only mode. (11387)


