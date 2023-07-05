---
title: Release Notes | What's New in Adobe Experience Manager Guides, June 2023 release
description: Learn the new and enhanced features in June 2023 release of Adobe Experience Manager Guides as a Cloud Service
exl-id: ff6ac4a4-76a3-4b41-9da7-6a888de0eca5
---
# What's new in June 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in version June 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-2023.6.0.md) article.

## Broken Links report in the Web Editor

AEM Guides allows you to check the overall completeness of your technical documents and generate reports from the Web Editor. Now in June 2023 release AEM Guides provides you the feature to view and fix broken links. This is a very useful report which helps you manage your broken links. You can easily view the broken links present in your DITA map and also fix them. 
 ![](assets/broken-link-report.png){width="800" align="left"}

Once you fix a link, it is not displayed under the list of broken links.  

For more details, see [View and fix broken links](../user-guide/reports-web-editor.md#report-broken-links).

## Rename and Move files within the Repository view
 
Now you can also rename or move a file from the repository panel. This feature is very handy and helps manage your files easily from the Repository panel. You can select a file and rename or move it using the **Options** menu for the selected file. AEM Guides displays a success message when you move or rename a file.   

![](assets/rename-move-assets.png){width="650" align="left"}

For more details on the Options menu of a file, see the **Repository view** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Native PDF enhancements

### Add a watermark to PDF output for draft documents 

Now you can add a watermark to the PDF output of the document which is yet not approved. This watermark does not appear if you generate the PDF for the document in ‘Approved’ docstate. For example, you can add a watermark Draft for your PDF output.

For more details, see [Add a watermark to the PDF output for draft documents](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Support for language variables

AEM Guides provides support for language variables. You can use language variables to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output.
You can add the language variables or the localized version of the labels to the appropriate sections in your PDF output and in the output templates.
 
#### Language variables in the PDF output 

You can use the language variables to define localized labels for elements like Note, Caution, and Warning. You can update the value for these variables in one or more languages, and then the localized value is automatically picked in the PDF output. 
For example, you can present the label Note in your PDF output in the following ways:
 
- English: Note
- French: Remarque
- German: Hinweis 
 
#### Language variables in the output templates

If you wanted to create the PDF output in various languages, you had to create different PDF templates containing localized text for each language. Now with the language variables feature, you only need to create the template once. Then for any static text you need to localize, you can create corresponding language variables and use them in your template.
You can create language variables for longer text, such as a whole sentence or even a paragraph. You can also apply styles and use HTML markup to format these language variables.

For more details, view [Support for language variables](../web-editor/native-pdf-language-variables.md).

### Ability to use AEM metadata in PDF layouts

Metadata is the description or definition of your content. This metadata is stored in your source DITA map content. 

Now In AEM Guides you can also select the metadata properties of your assets and add them to the page layout. Then AEM Guides picks these metadata properties of your assets and publishes them in your PDF output. 

 
![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> AEM Guides also supports the metadata properties for your DITA maps. 

For more details, see [Add fields and metadata](../native-pdf/design-page-layout.md#add-fields-metadata).


## Schematron enhancements

### Use report statements to check for rules in Schematron

AEM Guides also now supports the report statements with the Schematron. A report statement generates a message when a test statement evaluates to true. For example, if you want the short description to be less than or equal to 150 characters, you can define a report statement to check the topics where the short description is more than 150 characters.

For more details, see [Use assert and report statements to check for rules](../user-guide/support-schematron-file.md#schematron-assert-report).

### Use Regex expressions

You can also use Regex expressions to define a rule with matches() function and then perform validation using the Schematron file.

For more details, see [Use Regex expresstions](../user-guide/support-schematron-file.md#schematron-assert-report).


### Define abstract patterns

AEM Guides also supports abstract patterns in Schematron. You can define generic abstract patterns and reuse these abstract patterns. Abstract patterns can simplify your Schematron schema and also help you manage and update your validation logic. 


For more details, see [Define abstract patterns](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Navigate from the Web Editor to the AEM Home page 

Now you can easily navigate from the Web Editor to the AEM Home page. 

![](assets/web-editor-launch-page.png){width="800" align="left"}

*  Click the **Guides** icon (![](assets/aem-guides-icon.png) ), to go back to the AEM Navigation page. 


For more details, see [AEM Navigation page](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ). 

## Handling hierarchical definitions of subject definitions and enumerations 

AEM Guides come with the powerful feature to create Subject scheme maps which are a specialized form of DITA maps that are used to define taxonomic subjects and controlled values. Now AEM Guides also allows you to define the subject definition in a map and the enumeration definitions in another map. You can then add the map reference and use the subject scheme.
The subject-enumeration references are resolved in the same map or the referenced map. 

For more details on the handling hierarchical definitions of subject definitions and enumerations, see the **Subject scheme** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Support for XLIFF format in translation

AEM Guides also provides the support for XML Localization Interchange File Format (XLIFF) format in translation. Now you can also choose to **Create a new XLIFF translation project** to convert the XML content into the XLIFF format.
Using this format,  you can export the content to the industry standard XLIFF format, and then provide the same to the translation vendors. For more details, see [Create a translation project](../user-guide/translate-documents-web-editor.md#create-translation-project).

 ![](assets/translation-project-types.png){width="350" align="left"}



## Improved Favorites panel

AEM Guides helps you create a collection or favorite list of your  files and folders and use them easily. Now **Options** menu is also available in the **Favorites** panel. You can rename the selected collection or delete it from the **Options** menu. You can select the **Refresh** option to get a fresh list of files or folders from the repository. You can also view the folder contents in the Assets UI.   
  
![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> You can also refresh the list using the **Refresh** icon on the top.

For more details on the **Options** menu of a Favorites collection, see the **Favorites** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Switch to the system theme

You can also now use the device theme. Using the **User Preferences**, you can configure AEM Guides to automatically switch between light and dark themes based on the theme of your device.  

![](assets/device-theme-user-preferences.png){width="550" align="left"}

For more details, see the **User Preferences** feature description in the [Main toolbar](../user-guide/web-editor-features.md#id2051EA0G05Z) section.
