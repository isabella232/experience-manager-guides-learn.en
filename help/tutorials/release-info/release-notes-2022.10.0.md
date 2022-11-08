---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, October 2022 release
description: Latest release of Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
---
# Latest release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the latest release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.10.183.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the latest release of AEM Guides as a Cloud Service.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service October 2022 release. 

### FrameMaker and FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Not compatible | 2020 Update 4 and above |
| | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 | 
|  |  |  |  |


## New features and enhancements

AEM Guides as a Cloud Service provides enhancements and new features in the latest release:


### Quick Generate panel

Now AEM Guides provides the **Quick Generate** panel which helps you quickly generate and view the output for presets created for your DITA map.

![Quick Generate icon](assets/quick-generate-icon.png)

In the **Quick Generate** panel, you can see the list of all the output presets created for your DITA map. 

![Quick Generate panel](assets/quick-generate-panel.png)

Select one or more presets and quickly generate the output. You can also quickly view the output generated for the presets. A success message is displayed on the generation of the output. An error message is shown if the output generation fails. You can also view the error log to see the details of the error that occurred in the generation process.   


## Fixed issues

The bugs fixed in various areas are listed below:

* Native PDF | Error occurs on the removal of resource-only topics from the PDF output. (10554)
* Native PDF | Empty Keyrefs appear in the PDF output. (10553)
* Native PDF | `navtitle` for `topichead` is not honored. (10509)
* Native PDF | Support needed for amd64 JDK flavors. (10465)
* Native PDF | Not able to hide frontmatter topics from the Table of contents. (10355)
* Native PDF | Restarting the page number in the chapter layout randomly starts numbering from the end of the previous chapter. (10154)
* Chrome browser | Screen is getting blank on dragging and dropping any element from the UI. For example, on dragging a condition from the Conditions panel. (10524)
* Node properties are getting removed after the copy-paste operation of an asset. (10053)
* On clicking  **Close** users were being redirected to assets - the experience has been corrected to take users to the AEM homepage. (9654)
