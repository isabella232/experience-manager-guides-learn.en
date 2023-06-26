---
title: Release Notes | What's New in Adobe Experience Manager Guides, July 2023 release
description: Learn the new and enhanced features in July 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# What's new in July 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in version July 2023 version of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-2023.7.0.md) article.

## Connect to a data source and insert data into your topics

Now you can quickly connect to your data sources from AEM Guides. Connecting to a data source helps you to keep your information in sync and any updates to the data are reflected automatically. This feature helps you save your time and effort of manually adding or copying the data. 

Now, AEM Guides allows your administrator to configure the out-of-the-box connectors for JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases. They can also add other connectors by extending the default interfaces.

Once added, you can view the configured connectors listed under the **Data Sources** panel in the Web Editor.
 
![](assets/code-snippet-generator.png){width="300" align="left"}

You can create a content snippet generator to fetch the data from a connected data source . You can then insert the data into your topics, and edit it. 

Once you have created a content snippet generator, you can reuse it to insert the data into any topics. 

For more details, view [Insert a content snippet from your data source](../user-guide/web-editor-content-snippet.md).



## Review panel to showcase review projects and the active review tasks

Now AEM Guides makes your reviews more seamless. It provides the Reviews panel within the Web Editor. The Reviews panel displays all the review projects and the active review tasks within the review projects that you're part of.  

As an author this feature helps you to easily open the review tasks, view the comments, and also quickly address the comments in a centralized view. 
![](assets/active-review-task-comments.png){width="800" align="left"} 
For more details, view the **Review** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 


## Map Collection enhancements

A Map Collection helps you organize multiple maps and batch publish them. Many new enhancements have been made to the Map Collection:

- Now, you can also add Native PDF output presets to a map collection and use them to generate the PDF output. 
- You can view the global and folder profile presets created by your administrator and use them to generate the PDF output. 
- Now, you can not only select an individual preset, but you can also enable all the folder profile presets for a DITA map in one go.
![](assets/edit-map-collection.png){width="800" align="left"}   

For more details, view [Use Map Collection for output generation](../user-guide/generate-output-use-map-collection-output-generation.md).

## Ability to access temporary HTML files while generating the native PDF output

Now AEM Guides allows you to download the temporary HTML files created while generating the native PDF output. In the output preset settings, select the option to download the temporary files.  AEM Guides then allows you to download the temporary files created while generating the output using that preset. 

This features enables better insights into the generation process with access to interim styles and layouts and helps you correct or change your CSS styles according to your requirements. 

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

## Microservice-based publishing to generate HTML5 and Custom output

The new publishing microservice enables you to run large publishing workloads concurrently on AEM Guides as a Cloud Service and leverage the industry leading Adobe I/O Runtime serverless platform. Now using the microservice, you can also generate the HTML5 and the Custom output.
You can run multiple publishing requests and get an improved performance to generate these output formats.
For more details, view [Configure microservice-based publishing for AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## View AEM Guides version details in the About information

Now along with the AEM **About** information, you can also view the AEM Guides version details. You can view the current version details in the **About** option of the **Help** present on the AEM Navigation page. 

![](assets/about-aem-help.png)(width="800" align="left")