---
title: Release Notes | What's New in the Adobe Experience Manager Guides, December 2023 release
description: Learn the new and enhanced features in December 2023 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: c7316df1-8a73-4054-b2ba-5a4fcb989d5f
---
# What's new in the December 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in the version December 2023 of Adobe Experience Manager Guides (later referred to as *Experience Manager Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, view [Release Notes](release-notes-2023.12.0.md).


## Use variables in the Native PDF output 

You can use variable sets to dynamically insert and manage information that may change based on specific conditions such as product names and versions. This feature helps you use the same PDF layout and generate outputs with different values. You don’t have to create separate layouts for every set of values.

For example, you can create a variable set for each product. This variable set can consist of variables for different product details like ProductName, VersionNumber, and ReleaseDate. Then, you can add different values for these variables. 

**Variable set 1: Adobe-set1**

* ProductName: Experience Manager Guides 
* VersionNumber: 2311
* ReleaseDate: 11/02/2023

**Variable set 1: Adobe-set2**

* ProductName: Experience Manager Guides 
* VersionNumber: 2310
* ReleaseDate: 09/27/2023
 

![native pdf variables](assets/native-pdf-variables.png){width="800" align="left"}

*Create variables from the Output tab in the Web Editor.* 

You can also create variables with values having HTML tags. For example, add images from the content DAM using the `<img>` tag.

Once you have created the variables, you can add the variables to the appropriate places in your document using the page layouts in the output templates. The values are automatically picked in the PDF output based on the variable set you select in the output preset. 



<img src="./assets/native-pdf-variable-output.png" alt= "Footer in PDF output" width=500 border="2px">

*Generate the Native PDF output using variables in the PDF layout.*

This feature helps generate customized output with dynamic content in your documentation and manage changes efficiently. You can also apply styles and use HTML markup to format the variables.

You can also quickly update the values for any variable set whenever required and regenerate the output. For example, if you need to update the details for a version, you can update the value of the version in VersionNumber and regenerate the output. 


## Revamped experience to edit the attributes 

Now, you get a revamped experience to add or edit the attributes for an element from the **Content Properties** panel in the Web Editor. 

![Attributes panel](assets/attributes-multiple-properties.png){width="300" align="left"}

*Add attributes from the Content Properties panel.*

You can also easily edit and delete the attributes. 

For more details, refer to the **Content Properties** feature description within the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section.


## Edit metadata while authoring 

Now, while authoring, you can update the file metadata tags using the dropdown from the **File Properties** in the right panel. You can also select **Edit more properties** to update more metadata.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Update metadata and edit file properties from the right panel.*

For more details, refer to the **File Properties** feature description within the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section.

## Ability to publish content to the ServiceNow knowledge base

You can now also publish your content to the ServiceNow knowledge base platform.

With the December 2023 release, as an administrator, you can create a publish profile for the ServiceNow knowledge base server. Then, as an author or a publisher, you can choose that ServiceNow publish profile in the output preset to publish the output to the specified knowledge base.

This feature helps you publish content, like text, videos, and images, to the ServiceNow knowledge base platform and maintain a comprehensive repository.


![service now knowledge base preset](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Create an output preset for the ServiceNow knowledge base.*


## Enhanced Map collection dashboard

Experience Manager Guides provides an enhanced Map collection dashboard. In a map collection, you can quickly configure the metadata properties in bulk for the DITA maps. This feature is handy as you don’t have to update the metadata properties for each DITA map individually.
 
Now, you can view the filename of the DITA map. You can also view the Baselines. This helps you quickly find the baseline used for a preset.

![Map collection dashboard](assets/map-collection-dashboard.png){width="800" align="left"}

*View, edit, and generate output from the map collection dashboard.* 

Learn how to [use Map Collection for output generation](../user-guide/generate-output-use-map-collection-output-generation.md).

## View key attributes in the Map View

When you define key attributes for the topic or map references, you can also view the title, the corresponding icon, and the key in the left panel. The key is displayed as `key=<key-name>`.

For more details, refer to the **Map View** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

![keys in map view](assets/view-key-title-map-view.png) {width="300" align="left"}

*View the key attribute in the Map View.*

## Ability to duplicate a baseline based on label

Experience Manager Guides now provides an enhanced user experience for creating the baselines from the Web Editor.  
![create new baseline](assets/create-new-baseline.png) {width="300" align="left"}
*Create baseline from the Web Editor.*

It also allows you to duplicate a baseline based on the label. The reference version is picked based on the given label (if it exists) while duplicating, or else picks the version from the duplicated baseline.


![duplicate a baseline ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplicate a baseline based on a label or create an exact copy.*

## Improved process for the creation of bulk activation map collection

The process of creating a bulk activation map collection is now more harmonious. Now, when the Activation Results page is displayed, you can view the results of activation and logs. 
For more details, refer to [Create a bulk activation map collection](../user-guide/conf-bulk-activation-create-map-collection.md).



## Resolve cross-map links in the AEM Site output 

Cross-map links (XREF with scope peer) getting rendered in the AEM Site output are now resolved as per the file title of the publishing context set for the generated map.


## Configure the URL of the AEM Site output to use the document title

Experience Manager Guides allows you, as an administrator, to configure the URL of the AEM Site output. If the filename doesn’t exist or contains all special characters, you can configure to replace them with a separator in the URL of the AEM Site output. You can also replace them with the first child topic’s name. Learn how to [configure the URL of the AEM Site output to use the document title](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).
