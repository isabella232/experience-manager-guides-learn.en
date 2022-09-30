---
title: Release Notes | Adobe Experience Manager Guides 4.1 release
description: Latest release of Adobe Experience Manager Guides 
---
# Latest release of Adobe Experience Manager Guides

## Upgrade to the latest release

You can easily upgrade your current version of Adobe Experience Manager Guides (later referred as *AEM Guides*) to version 4.1. Before you proceed with upgrading to version 4.1 of AEM Guides, you must consider the following points:

* If you are using version 4.0.x, then you can directly upgrade to version 4.1. You need to upgrade to version 4.0.x before upgrading to 4.1.
* If you are using version 3.8.5, then you need to upgrade to version 4.0.x before upgrading to 4.1.
* If you are on a version prior to 3.8.5, refer to the upgrade section in the product-specific installation guide.

For details, see [Upgrade instructions](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1/Adobe-Experience-Manager-Guides_Upgrade-Instructions_EN.pdf).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides 4.1.2 release. 

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 12, 11, 10, or 9

**UUID**
Version 6.5 Service Pack 12, 11, 10, or 9

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
| 4.1 (Non-UUID)|  2.0 | 2.0 |  1.6 | 1.6  |
| 4.1 (UUID) | 2.7 | 2.7  |2.3 | 2.3  |
|  |  |  |  



## Fixed issues

The bugs fixed in various areas are listed below:

* On selecting all folder profiles, an invisible folder profile (which is incorrect) appears. (10393)
* Baseline creation does not pick the latest version, when the user's timezone is different from the server timezone. (10336) 
* Control+F shortcut is not opening the browser search modal on the Assets Console after the installation of AEM Guides 4.1. (10339)
* Baseline creation error occurs for the topic which has the reference to a folder. (10383)
* Output presets tab is showcasing a blank screen intermittently and in some cases non editable presets are getting displayed. (10390)
* Keyspace management is leading to exceptions and errors. (10449)