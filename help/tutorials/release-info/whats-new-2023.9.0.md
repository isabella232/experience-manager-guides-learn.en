---
title: Release Notes | What's New in Adobe Experience Manager Guides, September 2023 release
description: Learn the new and enhanced features in September 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# What's new in September 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in version  September 2023 of Adobe Experience Manager Guides (later referred to as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see [Release notes](release-notes-2023.9.0.md).

## Connect to a data source and insert the topics

AEM Guides provides out-of-the-box connectors that help you connect with your data sources, making AEM Guides a true content hub. This gives you the advantage of saving you time and effort that would otherwise be spent on manual data addition or replication.

Along with the existing out-of-the-box connectors like JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite), your administrator can also configure connectors like MariaDB, H2DB, AdobeCommerce, and ElasticSearch databases. They can also add other connectors by extending the default interfaces.

You can view the configured connectors under the **Data Sources** panel in the Web Editor.
 
<img  src="assets/data-sources.png" alt= "Data sources list in the panel" width=300>

*View the connected data sources.*

You can now also create a topic from a connected data source. A topic can contain data in various formats, like tables, lists, and paragraphs. It also allows you to create a DITA map for all topics. You can associate metadata to the topic when pulling from a data source.

For more details, view [Use data from your data source](../user-guide/web-editor-content-snippet.md).

## Add citations to your content

Citations are references to the source of information added to your content. Citations assist you in establishing credibility and preventing plagiarism. Citations help the readers to locate the source and verify the information presented in the text.

In AEM Guides, you can add citations or import citations and apply them to your content. You can add these citations from any source of books, websites, and journals. 

After inserting your citations to your topics, you can preview them in the Web Editor. You can also publish content with citations using Native PDF.

![Citations listed in a panel](assets/citation-panel.png){width="300" align="left"}

*View the list of citations in the Citations panel.*

For more details, view [Add and manage citations in your content](../user-guide/web-editor-apply-citations.md).


## Publish to a content fragment

Content fragments are discrete pieces of content in AEM. They are structured content based on a content model. Content fragments are pure content without design or layout information. They can be authored and managed independently of the channels that AEM supports. The modularity and reusability of the content fragments leads to greater flexibility, consistency, efficiency, and simpler management.

Now AEM Guides offers a way to publish a topic or the elements within a topic to a content fragment. You can create a JSON-based mapping between a topic and a content fragment model. Use this mapping to publish content present in some or all elements within a topic to a content fragment. 

Capitalize the power of AEM Guides and content fragments and use content fragments in any AEM site. You can also extract the details via APIs supported by content fragments.

![option to publish content fragment](assets/content-fragment-publish.png){width="550" align="left"}

*Publish a topic to a content fragment.*

For more details, view [Publish to a content fragment](../user-guide//publish-content-fragment.md).

## Review Enhancements

AEM Guides now provides an improved review capability with the following functionalities:

### Search review topics 

Conducting reviews is a critical feature of AEM Guides. It helps the reviewers to review the documents assigned to them . 
Now you can search for a topic by entering some part of the text of the title or filepath in the search bar of the topics view of the review panel. You can also choose to view all topics or view topics with comments. By default, you can view all topics present in the review task. For more details, view [Review topics](../user-guide/review-topics.md).

![Search in a review topics panel](assets/review-search-topic.png){width="800" align="left"}
*Search a review topic in the review panel.*



## Guides Extension Framework 

Create custom packages on top of AEM Guides to provide extensibility using AEM Guides Extension Framework. These packages are useful for developers and consultants and give them extensibility to the components in the Editor. They can target buttons, dialogs, and dropdowns and add custom JavaScript that can easily interoperate with AEM Guides UI.



## Native PDF enhancements

The following Native PDF enhancements have been done in the September 2023 release to make AEM Guides a more robust product:



### Order pages in the PDF output

You can show or hide the following sections in your PDF and also arrange the order in which they should appear in your final PDF output:

* TOC
* Chapters & Topics
* List of Figures
* List of Tables
* Index
* Glossary
* Citation
* Page layouts

If you do not want to show a particular section in your PDF output, you can hide that by turning the toggle switch off.

For more details, view [Page Order](../native-pdf/components-pdf-template.md#page-order).

### Merge pages

In a Native PDF output by default, all sections begin on a new page. Now you can merge a section to its previous page or the next page. This publishes the section in continuation with the selected page in the PDF output and there is no page break-in between.

For more details, view the **Merge pages** feature description in [Page Order](../native-pdf/components-pdf-template.md#page-order) section.

### Start any chapter from the current page

You can set the basic configuration settings for starting a chapter from odd or even page, the TOC structure, and define the leader line format for the TOC entries. 

Now you can also start a chapter from the current page. If you choose to do so, all chapters are published in continuation without any page breaks. For example, if a chapter ends in the middle of page 15, then the next chapter also starts from the 15th page itself.

For more details, view the **General** tab description in  [Advanced PDF Settings](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Static pages

You can also create custom page layouts and publish them as static pages in the PDF output. This helps you to add any static content like Notes or blank pages. 

For more details, view the **Static pages** feature description in [Page Order](../native-pdf/components-pdf-template.md#page-order) section.


### Variables in cross references

You can use variables to define a cross-reference. When you use a variable, its value is picked from the properties.

Now you can also use {figure} and {table}.
Use {figure}to add a cross-reference to the figure number. It picks the figure number from the auto number styles that you’ve defined for figcaption. 

Use {table} to add a cross-reference to the table number. It picks the table number from the auto number styles that you’ve defined for caption.

For more details, view [Cross references](../native-pdf/components-pdf-template.md##cross-references).



### Redesign of CSS editor

Now the CSS editor is redesigned for a better user experience with selectors and style properties.

#### Enhancement of Add Style dialog

You can now use custom selectors to add complex styles. The new Selector field helps you to add custom selectors besides the Class, Tag, and Pseudo Class combination. For example, you can create `table a.link` style for all the hyperlinks inside a table.

![adding styles in the native pdf templates](assets/add-styles-native-pdf.png){width="300" align="left"}

*Add the details for the new style.*

#### Customize properties of style

Now AEM Guides introduces you to a new properties panel under the preview section for styles. You can edit the properties of the styles more efficiently and quickly from the properties panel.


## Support for multiple subject definitions in a single enumeration definition

You can now define one or more subject definitions in one map and the enumeration definitions in another map and then add the map reference. The subject-enumeration references are resolved in the same map or the referenced map.

You can now also define conditions and apply them to some specific elements in a topic.  The conditions are visible only for those specific elements and not for all the other elements.

For more details on the handling hierarchical definitions of subject definitions and enumerations, view the Subject scheme feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.





## Select all presets in a Map Collection

You can not only enable an individual preset and all folder profile presets, but also enable all the presets for a DITA map in one go.
![edit a map collection](assets/edit-map-collection-cs.png){width="800" align="left"}   
*Select all presets in a map collection.*

For more details, view [Use Map Collection for output generation](../user-guide/generate-output-use-map-collection-output-generation.md).


## Native PDF support in Bulk Publish Dashboard


With AEM Guides' Bulk Activation feature, you can quickly and easily activate your content from authoring to publishing instance. In the Bulk Activation map, you can include the Native PDF output preset, the AEM Site, PDF, HTML5, Custom, and JSON output.
For more details, view [Bulk activation of published content](../user-guide/conf-bulk-activation.md).

## Improved Bulk Move Tool

Now as an administrator, you can use the improved Bulk Move Tool to move folders with many files from one location to another. 
You can use the browse file dialog to select the source folders you want to move. You can also browse to select the destination location to move the source folders. Select ![info icon](assets/info-icon.svg) {width="25" align="left"} near a field to view more information about it.

For more details, view [Move files in bulk](../user-guide/authoring-file-management.md#move-files-bulk).


## Enhanced preview experience from the context menu

Use the context menu to quickly preview the file (.dita, .xml, audio, video, or image) without opening it. You can now resize the preview pane, and if the content contains any reference link, you can select it to open it in a new tab. 

![Preview pane ](assets/quick-preview_cs.png){width="800" align="left"}

*Preview the file in the pane.*

For more details on the context menu, see the **Options for a file** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.


## Use variables for current date and time in the  Destination Path, Site Name, or File Name options

While generating outputs in AEM Site or PDFs, you can use variables for setting the **Destination Path**, **Site Name**, or **File Name** options. You can now also use the `${system_date}`and `${system_time}` variables. These variables help you append the current date and time to these options.


