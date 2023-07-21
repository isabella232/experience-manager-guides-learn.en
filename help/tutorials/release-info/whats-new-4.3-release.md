---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.3 release
description: Learn the new and enhanced features in 4.3 releases of Adobe Experience Manager Guides
---
# What's new in 4.3 release of Adobe Experience Manager Guides (July 2023)

This article covers the new and enhanced features in version 4.3 of Adobe Experience Manager Guides (later referred as *AEM Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](./release-notes-4.3.md).


## Connect to a data source and insert data into your topics

Now you can quickly connect to your data sources using out-of-the-box connectors from AEM Guides. Connecting to a data source enables you to keep your information in sync with the source, and any updates to the data are reflected automatically, making AEM Guides a true content hub. This feature helps you save time and effort to manually add or copy the data.

AEM Guides allows your administrator to configure the out-of-the-box connectors for JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases. They can also add other connectors by extending the default interfaces.
Once added, you can view the configured connectors listed under the Data Sources panel in the Web Editor.
 
<img  src="assets/data-sources.png" alt= "Data sources list in the panel" width=300>

Create a content snippet to fetch the data from a connected data source. You can then insert the data into your topics and edit it. Once you’ve created a content snippet generator, you can reuse it to insert the data into any topic. 

Now you can also create a topic from a connected data source.  A topic can contain data in various formats, like tables, lists, and paragraphs. It also allows you to create a DITA map for all topics.  You can associate metadata to the topic when pulling from a data source.

For more details, view [Use data from your data source](../user-guide/web-editor-content-snippet.md).

## Add citations to your content

Citations are references to the source of information added to your content. Citations assist you in establishing credibility and preventing plagiarism. Citations help the readers to locate the source and verify the information presented in the text.

In AEM Guides, you can add citations or import citations and apply them to your content. You can add these citations from any source of books, websites, and journals. 

After inserting your citations to your topics, you can preview them in the Web Editor. You can also publish content with citations using Native PDF.

![Citations listed in a panel](assets/citation-panel.png){width="300" align="left"}


For more details, view [Add and manage citations in your content](../user-guide/web-editor-apply-citations.md).

## Publish to a content fragment

Content fragments are discrete pieces of content in AEM. They are structured content based on a content model. Content fragments are pure content without design or layout information. They can be authored and managed independently of the channels that AEM supports. The modularity and reusability of the content fragments leads to greater flexibility, consistency, efficiency, and simpler management.

Now AEM Guides offers a way to publish a topic or the elements within a topic to a content fragment. You can create a JSON-based mapping between a topic and a content fragment model. Use this mapping to publish content present in some or all elements within a topic to a content fragment. 

Capitalize the power of AEM Guides and content fragments and use content fragments in any AEM site. You can also extract the details via APIs supported by content fragments.

![option to publish content fragment](assets/content-fragment-publish.png){width="550" align="left"}


## Review Enhancements
AEM Guides now provides an improved review capability with the following functionalities:

### Review panel to showcase review projects and the active review tasks

Now AEM Guides makes your reviews more seamless. It provides the Reviews panel within the Web Editor. The Reviews panel displays all the review projects and the active review tasks within the review projects that you're part of.  

As an author, this feature helps you easily open the review tasks, view the comments, and quickly address the comments in a centralized view. 
![](assets/active-review-task-comments.png){width="800" align="left"} 
For more details, view the **Review** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

### Search review topics 

Conducting reviews is a critical feature of AEM Guides. It helps the reviewers to review the documents assigned to them . 
Now you can search for a topic by entering some part of the text of the title or filepath in the search bar of the topics view of the review panel. You can also choose to view all topics or view topics with comments. By default, you can view all topics present in the review task.


![Search in a review topics panel](assets/review-search-topic.png){width="800" align="left"}

For more details, view [Review topics](../user-guide/review-topics.md).

## Guides Extension Framework 

Create custom packages on top of AEM Guides to provide extensibility using AEM Guides Extension Framework. These are useful for developers and consultants and give them extensibility to the components in the Editor. They can target buttons, dialogs, and dropdowns and add custom JavaScript that can easily interoperate with AEM Guides UI.



## Native PDF enhancements
The following Native PDF enhancements have been done in the 4.3 release to make AEM Guides a more robust product:

### Support for language variables

AEM Guides provides support for language variables. You can use language variables to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output.
You can add the language variables or the localized version of the labels to the appropriate sections in your PDF output and in the output templates.
 
#### Language variables in the PDF output 

You can use the language variables to define localized labels for elements like Note, Caution, and Warning. You can update the value for these variables in one or more languages, and then the localized value is automatically picked in the PDF output. 
For example, you can present the label Note in your PDF output in the following ways:
 
* English: Note
* French: Remarque
* German: Hinweis 
 
#### Language variables in the output templates

If you wanted to create the PDF output in various languages, you had to create different PDF templates containing localized text for each language. Now with the language variables feature, you only need to create the template once. Then for any static text you need to localize, you can create corresponding language variables and use them in your template.
You can create language variables for longer text, such as a whole sentence or even a paragraph. You can also apply styles and use HTML markup to format these language variables.

For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).

### Add a watermark to PDF output for draft documents 

Now you can add a watermark to the PDF output of the document which is yet not approved. This watermark does not appear if you generate the PDF for the document in ‘Approved’ docstate. For example, you can add a watermark Draft for your PDF output.

For more details, see [Add a watermark to the PDF output for draft documents](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Ability to use AEM metadata in PDF layouts

Metadata is the description or definition of your content. This metadata is stored in your source DITA map content. 

Now In AEM Guides you can also select the metadata properties of your assets and add them to the page layout. Then AEM Guides picks these metadata properties of your assets and publishes them in your PDF output. 

 
![add metadata for native pdf](assets/native-pdf-metadata-asset.png){width="300" align="left"}

>[!NOTE]
>
> AEM Guides also supports the metadata properties for your DITA maps. 

For more details, see [Add fields and metadata](../native-pdf/design-page-layout.md#add-fields-metadata).


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

In a Native PDF output by default, all sections begin on a new page. Now you can merge a section to its previous page or the next page.  This publishes the section in continuation with the selected page in the PDF output and there is be no page break in between.

For more details, view Merge pages feature description in [Page Order](../native-pdf/components-pdf-template.md#page-order) section.

### Static pages

You can also create custom page layouts and publish them as static pages in the PDF output. This helps you to add any static content like Notes or blank pages. 

For more details, view Static pages feature description in [Page Order](../native-pdf/components-pdf-template.md#page-order) section.


### Variables in cross references

You can use variables to define a cross-reference. When you use a variable, its value is picked from the properties.

Now you can use  also use {figure} and {table}.
Use {figure}to add a cross-reference to the figure number. It picks the figure number from the auto number styles that you’ve defined for figcaption. 

Use {table} to add a cross-reference to the table number. It picks the table number from the auto number styles you’ve defined for caption.

For more details, view [Cross references](../native-pdf/components-pdf-template.md##cross-references).

### Start any chapter from the current page

You can set the basic configuration settings for starting a chapter from odd or even page, the TOC structure, and define the leader line format for the TOC entries. 

Now you can also start a chapter from the current page.  If you choose to do so, all chapters are published in continuation without any page breaks. For example, if a chapter ends in the middle of page 15, then the next chapter also starts from the 15th page itself.


### Ability to access temporary HTML files while generating the native PDF output

Now AEM Guides allows you to download the temporary HTML files created while generating the native PDF output. In the output preset settings, select the option to download the temporary files.  AEM Guides then allows you to download the temporary files created while generating the output using that preset. 

This feature enables better insights into the generation process with access to interim styles and layouts and helps you correct or change your CSS styles according to your requirements. 

![the advnaced settings dialog of native pdf](assets/native-pdf-advanced-settings.png){width="800" align="left"}

For more details, view [Create a PDF output preset](../web-editor/native-pdf-web-editor.md#create-output-preset).   

## Rename and Move files within the Repository view
 
Now you can also rename or move a file from the repository panel. This feature is handy and helps manage your files easily from the Repository panel. You can select a file and rename or move it using the **Options** menu for the selected file. AEM Guides displays a success message when you move or rename a file.   

![options menu of a file](assets/rename-move-assets.png){width="550" align="left"}

For more details on the Options menu of a file, see the **Repository view** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Broken Links report in the Web Editor

AEM Guides allows you to check the overall completeness of your technical documents and generate reports from the Web Editor. Now in June 2023 release AEM Guides provides you the feature to view and fix broken links. This is a  useful report which helps you manage your broken links. You can easily view the broken links present in your DITA map and also fix them. 
 ![broken link report](assets/broken-link-report.png){width="800" align="left"}

Once you fix a link, it is not displayed under the list of broken links.  

For more details, see [View and fix broken links](../user-guide/reports-web-editor.md#report-broken-links).

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

## Support for XLIFF format in translation

AEM Guides also provides the support for XML Localization Interchange File Format (XLIFF) format in translation. Now you can also choose to **Create a new XLIFF translation project** to convert the XML content into the XLIFF format. AEM Guides supports XLIFF version 1.2.

Using this format,  you can export the content to the industry standard XLIFF format, and then provide the same to the translation vendors. For more details, see [Create a translation project](../user-guide/translate-documents-web-editor.md#create-translation-project).

 ![types of translation projects](assets/translation-project-types.png){width="350" align="left"}


## Map Collection enhancements

A Map Collection helps you organize multiple maps and batch publish them. Many new enhancements have been made to the Map Collection:

* Now, you can also add Native PDF output presets to a map collection and use them to generate the PDF output. 
* You can view the global and folder profile presets created by your administrator and use them to generate the PDF output. 
* Now, you can not only select an individual preset, but you can also enable all the folder profile presets for a DITA map in one go.
![edit a map collection](assets/edit-map-collection.png){width="800" align="left"}   

For more details, view [Use Map Collection for output generation](../user-guide/generate-output-use-map-collection-output-generation.md).

## Native PDF support in Bulk Publish Dashboard


With AEM Guides' Bulk Activation feature, you can quickly and easily activate your content from authoring to publishing instance. In the Bulk Activation map, you can include the Native PDF output preset, the AEM Site, PDF, HTML5, Custom, and JSON output.
For more details, view [Bulk activation of published content](../user-guide/conf-bulk-activation.md).

## Improved Bulk Move Tool

Now as an administrator, you can use the improved Bulk Move Tool to move folders with many files from one location to another. 
You can use the browse file dialog to select the source folders you want to move. You can also browse to select the destination location to move the source folders. Select ![info icon](assets/info-icon.svg) {width="25" align="left"} near a field to view more information about it.

For more details, view [Move files in bulk](../user-guide/authoring-file-management.md#move-files-bulk).


## Add labels during file check-in using Oxygen Plugin for AEM Guides

Oxygen Plugin for AEM Guides allows you to add labels to different versions of a file while checking in a file from your local system into AEM repository.
If your administrator has predefined a list of labels and uploaded them in the label.json file, you can choose one or more labels from the list.

## Improved Favorites panel

AEM Guides helps you create a collection or favorite list of your  files and folders and use them easily. Now **Options** menu is also available in the **Favorites** panel. You can rename the selected collection or delete it from the **Options** menu. You can select the **Refresh** option to get a fresh list of files or folders from the repository. You can also view the folder contents in the Assets UI.   
  
![the favorites panel](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> You can also refresh the list using the **Refresh** icon on the top.

For more details on the **Options** menu of a Favorites collection, see the **Favorites** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Switch to the system theme

You can also now use the device theme. Using the **User Preferences**, you can configure AEM Guides to automatically switch between light and dark themes based on the theme of your device.  

![user preferences](assets/device-theme-user-preferences.png){width="550" align="left"}

For more details, see the **User Preferences** feature description in the [Main toolbar](../user-guide/web-editor-features.md#id2051EA0G05Z) section.
