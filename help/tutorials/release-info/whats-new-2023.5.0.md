---
title: Release Notes | What's New in in Adobe Experience Manager Guides, May 2023 release
description: Learn the new and enhanced features in May 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# What's new in May 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in May 2023 version of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-2023.5.0.md) article.

## Broken Links report in the Web Editor

AEM Guides allows you to check the overall completeness of your technical documents and generate reports from the Web Editor. Now in May 2023 release AEM Guides provides you the feature to view and fix broken links. This is a very useful report which helps you manage your broken links. You can easily view the broken links present in your DITA map and also fix them. 
 ![](assets/broken-link-report.png){width="800" align="left"}

Once you fix a link, it is not displayed under the list of broken links. Instead, you can see it under the **Topic List** or **Metadata**.  

For more details, see [View and fix broken links](../user-guide/reports-web-editor.md#report-broken-links).

## Rename and Move files within the Repository view
 
Now you can also rename or move a file from the repository panel. This feature is very handy and helps manage your files easily from the Repository panel. You can select a file and rename or move it using the Options menu for the selected file. AEM Guides displays a success message when you move or rename a file. However, you cannot rename a file to a name that already exists. Also, you cannot move a file to a folder where a file with the same name already exists.  

![](assets/rename-move-assets.png){width="650" align="left"}

For more details on the Options menu of a file, see the **Repository view** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.


## Handling hierarchical definitions of subject definitions and enumerations 

AEM Guides come with the powerful feature to create Subject scheme maps which are a specialized form of DITA maps that are used to define taxonomic subjects and controlled values. Now AEM Guides also provides the feature to define the subject definition in a map and the enumeration definitions in another map. You can then add the map reference and use the subject scheme.
The subject-enumeration references are resolved in the same map or the referenced map. 

For more details on the handling hierarchical definitions of subject definitions and enumerations, see the **Subject scheme** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.


## Options menu for the Favorites panel

AEM Guides also provides you with the **Options** menu for the **Favorites** panel. You can rename the selected collection or delete it from the **Options** menu. You can also view the folder contents in the Assets UI. You can select the Refresh option to get a fresh list of files or folders from the repository.   
  
![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> You can also refresh the list using the **Refresh** icon on the top.

For more details on the **Options** menu of a Favorites collection, see the **Favorites** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Switch to the system theme

You can also now use the device theme. Using the **User Preferences**, you can configure AEM Guides to automatically switch between light and dark themes based on the theme of your device.  

![](assets/device-theme-user-preferences.png){width="550" align="left"}

For more details, see the **User Preferences** feature description in the [Main toolbar](../user-guide/web-editor-features.md#id2051EA0G05Z) section.

## Use Report statements to check for rules in Schematron

AEM Guides also now supports the report statements with the Schematron. A report statement generates a message when a test statement evaluates to true. For example, if you want the short description to be less than or equal to 150 characters, you can define a report statement to check the topics where the short description is more than 150 characters.

For more details, see [Use Assert and Report statements to check for rules](../user-guide/support-schematron-file.md#schematron-assert-report).

## Define abstract patterns

AEM Guides also supports abstract patterns in Schematron. You can define generic abstract patterns and reuse these abstract patterns. Abstract patterns can simplify your Schematron schema and also help you manage and update your validation logic. 


For more details, see [Define abstract patterns](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Navigate from the Web Editor to the AEM homepage 

Now you can easily navigate from the Web Editor to the AEM Navigation page. 

![](assets/web-editor-launch-page.png){width="800" align="left"}

*  Click the **Guides** icon (![](assets/aem-guides-icon.png) ), to go back to the AEM Navigation page. 


For more details, see [AEM Navigation page](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ). 

## Native PDF enhancements

### Native PDF | Add a watermark to PDF output for draft documents 

Now you can add a watermark to the PDF output of the document which is yet not approved. This watermark does not appear if you generate the PDF for the document in ‘Approved’ docstate. For example, you can add a watermark Draft for your PDF output.

### Native PDF | Support for language variables in DITA elements

AEM Guides provides support for the language variables. These variables are very useful to generate localized strings for elements like note, tip, warning, caution. For example, you can have the following ways to present your NOTE in the PDF output:
German: Notiz
Spanish: Nota
Native PDF | Support for language variables in your page footer
You can add a language variable to a running header or footer on the master page of a document. The variable displays across all body pages of the document that have this master page applied. For example, 1 of 1 page.
You can also use it to present the numbers in various languages.

### Native PDF | Localized prefixes for your TOC

You also have the feature to display localized terms to be used to present the prefixes in your headings. 
For example, you can have the following ways to present your ‘Chapter’ prefix in the PDF output:
German: Kapitel
Spanish: Capítulo

### Native PDF | Add metadata properties for assets

Metadata is the description or definition of your content. You can also add metadata information as variables or fields in your page layout. This metadata is stored in your source DITA map content, and it can be easily inserted into your page layout for the PDF output. 
Now you can also select the metadata properties of your assets and add them to the page layout. Then AEM Guides picks these metadata properties of your assets and publishes them in your PDF output. 
 
![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> These properties are set from the Properties page of the DITA map or bookmap file.  

