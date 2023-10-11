---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.3.1 release
description: Learn about the new and enhanced features in 4.3.1 releases of Adobe Experience Manager Guides
---
# What's new in 4.3.1 release of Adobe Experience Manager Guides (October 2023)

This article covers the new and enhanced features in version 4.3.1 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see [Release notes](./release-notes-4.3.1.md).

## Connect to a data source and insert the topics

Experience Manager Guides provides out-of-the-box connectors that help you connect with your data sources, making AEM Guides a true content hub. This gives you the advantage of saving you time and effort that would otherwise be spent on manual data addition or replication.

Along with the existing out-of-the-box connectors like JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite), your administrator can also configure connectors for MariaDB, H2DB, AdobeCommerce, and ElasticSearch databases. They can also add other connectors by extending the default interfaces.

You can view the configured connectors under the **Data Sources** panel in the Web Editor.
 
<img  src="assets/data-sources.png" alt= "Data sources list in the panel" width=300>

*View the connected data sources.*

You can now also create a topic from a connected data source. A topic can contain data in various formats, like tables, lists, and paragraphs. It also allows you to create a DITA map for all topics. You can associate metadata to the topic when pulling from a data source.

For more details, view [Use data from your data source](../user-guide/web-editor-content-snippet.md).

## Configure a data source connector from the user interface

Experience Manager Guides now also provides a **Data Sources** tool that helps you configure out-of-the-box connectors for data sources. You can easily create the connectors for JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, and ElasticSearch databases.

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


## Support for multiple subject definitions in a single enumeration definition

You can now define one or more subject definitions in one map and the enumeration definitions in another map and then add the map reference. The subject-enumeration references are resolved in the same map or the referenced map.

You can now also define conditions and apply them to some specific elements in a topic.  The conditions are visible only for those specific elements and not for all the other elements.

For more details on the handling hierarchical definitions of subject definitions and enumerations, view the Subject scheme feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.




## Enhanced preview experience from the context menu

Use the context menu to quickly preview the file (.dita, .xml, audio, video, or image) without opening it. You can now resize the preview pane, and if the content contains any reference link, you can select it to open it in a new tab. 

![Preview pane ](assets/quick-preview_cs.png){width="800" align="left"}

*Preview the file in the pane.*

For more details on the context menu, see the **Options for a file** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Edit a file in the Oxygen connector plugin

Experience Manager Guides now allows you to select a file in the Web Editor and then choose to edit the file in the Oxygen connector plugin. This option isn't enabled as a part of the out-of-the-box support. 

For more details, refer to the **Options for a file** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Use variables for current date and time in the  Destination Path, Site Name, or File Name options

While generating outputs in AEM Site or PDFs, you can use variables for setting the **Destination Path**, **Site Name**, or **File Name** options. You can now also use the `${system_date}`and `${system_time}` variables. These variables help you append the current date and time to these options.

Learn how to [use variables for setting the Destination Path, Site Name, or File Name options](../user-guide/generate-output-use-variables.md).
