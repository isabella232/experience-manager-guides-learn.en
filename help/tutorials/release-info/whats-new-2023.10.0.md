---
title: Release Notes | What's New in Adobe Experience Manager Guides, October 2023 release
description: Learn the new and enhanced features in October 2023 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
---
# What's new in October 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in the version  October 2023 of Adobe Experience Manager Guides (later referred to as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see [Release notes](release-notes-2023.10.0.md).


## Configure a data source connector from the user interface

Experience Manager Guides now provides a **Data Sources** tool that helps you configure out-of-the-box connectors for data sources. You can easily create the connectors for JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, and ElasticSearch databases.

You can also easily edit, reconnect, duplicate, or delete a data source connector. Learn how to [easily configure a data source connector from the user interface](../cs-install-guide/conf-data-source-connector-tools.md).

![data source connectors listed in the data sources panel](assets/data-sources-create-window.png){width="550" align="left"}

*Create and view the data source connectors from the data sources panel.*

## View logs for the topic generator

You can now also view the content generation log file. This log file helps you check the warnings, errors, and exceptions.  Learn more about how the [options for a topic generator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) help you easily generate and manage the topic generators.   

## Support for Velocity tools in the data source templates

You can now use the Velocity tools in the Experience Manager Guides templates. These tools help you apply various functions to the data you fetch from the data sources. You can use the templates while creating a content snippet or a topic. This feature helps you save time and effort to manually apply the same function to each data set.  It also ensures accurate results. 
For example, you can use the $mathTool to perform mathematical functions. 
Learn more about how to [use Velocity tools in the data source templates](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Native PDF enhancements

The following Native PDF enhancements have been done in the October 2023 release:

### Reset the page number for the first page of a layout

In the native PDF output, you can restart the page numbers and specify the number from which the numbering begins. Now you can also start the numbering only for the first occurrence of a section. 
Learn more about how to [work with the page properties of a page layout](../native-pdf/design-page-layout.md#page-props-page-layout). 


### View chapters without auto numbers in the TOC

Experience Manager Guides display the chapter numbers along with the chapter names in the Table of Contents (TOC). Now you can choose to publish only the chapter names without the chapter numbers. View more details about how to configure the [advanced PDF settings of a template](../native-pdf/components-pdf-template.md#advanced-pdf-settings). 

## Download a map from the Web Editor

Now you can not only edit a map in the map view of the Web Editor but also download it. You can choose to download the map using a specific baseline. You also have the option to flatten the hierarchy and save all the files and folders in a single folder. 

For more details, refer to the **Map View** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

![options menu of a file in the repository view](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Select a file in repository view and choose the option to perform an action on the file.* 

## Edit a file in the Oxygen connector plugin

Experience Manager Guides now allows you to select a file in the Web Editor and then choose to edit the file in the Oxygen connector plugin. This option isn't enabled as a part of the out-of-the-box support. 

For more details, refer to the **Options for a file** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.
