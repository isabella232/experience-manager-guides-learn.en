---
title: Release Notes | What's New in the Adobe Experience Manager Guides, December 2023 release
description: Learn the new and enhanced features in December 2023 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the December 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in the version December 2023 of Adobe Experience Manager Guides (later referred to as *Experience Manager Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, view [Release Notes](release-notes-2023.12.0.md).




## Edit metadata while authoring 

Now, you can manage the file properties more easily from the Web Editor. You can seamlessly update the file metadata using the dropdown from the **File Properties** in the right panel. You can also edit more properties quickly from the **File Properties**.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Update metadata and edit file properties from the right panel.*

For more details, refer to the **File Properties** feature description within the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section.



## Propagate asset metadata to the published Native PDF output 

Now, you can set and update the metadata for a DITA map from the Native PDF output preset. Once set, these properties are also copied into the topics within the map and passed to the output generated using Native PDF.
 
![file-properties](assets/output-preset-file-poperties.png){width="500" align="left"}

*Set file properties from the Native PDF output preset.*


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

*Generate the native PDF output using variables in the PDF layout.*

You can also quickly update the values for any variable set whenever required. For example, if you need to update the details for a version, you can update the value of the version in VersionNumber. 

This feature helps generate customized output with dynamic content in your documentation and manage changes efficiently. You can also apply styles and use HTML markup to format the variables.



## Support for ServiceNow knowledge base site path in publishing

Experience Manager Guides now provides the support to publish your content to the ServiceNow knowledgebase platform. With the December 2023 release, your administrator can create a publish profile for the ServiceNow knowledgebase server. 

While creating the output preset for a DITA map, you have the additional option to choose the ServiceNow Knowledge Base as the target. You can choose the ServiceNow publish profile in the output preset to generate the output for the map to the specified Knowledgebase.
This feature helps you publish various content, like text, videos, and images, to the ServiceNow knowledgebase platform and maintain a comprehensive repository.

![publish profile in editor settings](assets/editor-settings-publish-profile-servicenow.png){width="500" align="left"}

*Create a publish profile for the ServiceNow knowledgebase server.*


## Enhanced experience while selecting attributes from the Content Properties 

Experience Manager Guides provides an enhanced experience while you select and add one or more properties to an element from the **Attributes** panel in the Content Properties. 

![Attributes panel](assets/attributes-multiple-properties.png){width="300" align="left"}

*Add attributes from the Content Properties.*

You can easily select the attribute and the values from the dropdowns. You can also easily edit and delete an attribute from the **Attributes** panel. 

For more details, refer to the **Content Properties** feature description within the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section.


## Enhanced Map collection dashboard

Experience Manager Guides provides an enhanced Map collection dashboard. In a map collection, you can quickly configure the metadata properties in bulk for the DITA maps. This feature is handy as you don’t have to update the metadata properties for each DITA map individually.
 
Now, you can view the filename of the DITA map. You can also view the Baselines. This helps you quickly find the baseline used for a preset.

![Map collection dashboard](assets/map-collection-dashboard.png){width="800" align="left"}

*View, edit, and generate output from the map collection dashboard.* 

## An improved process for the creation of bulk activation map collection

The process of creating a bulk activation map collection is now more harmonious. Now, when the Activation Results page is displayed, you can view the results of activation and logs. 
For more details, refer to [Create a bulk activation map collection](../user-guide/conf-bulk-activation-create-map-collection.md).


## View key attribute in the Map View

When you define key attributes for the topic or map references, you can also view the title, the corresponding icon, and the key in the left panel. The key is displayed as `key=<key-name>`.

For more details, refer to the **Map View** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

![keys in map view](assets/view-key-title-map-view.png) {width="300" align="left"}

*View the key attribute in the Map View.*

## Resolve cross-map links in the AEM Site output 

Cross-map links (XREF with scope peer) getting rendered in the AEM Site output are now resolved as per the file title of the publishing context set for the generated map.


## Duplicate baselines based on labels

Experience Manager Guides allows you to duplicate a baseline based on the label. The reference version is picked based on the given label (if it exists) while duplicating, or else picks the version from the duplicated baseline.

## Configure page names for topic titles 

Experience Manager Guides allows you, as an administrator, to configure the page names for the topics. If the filename doesn’t exist or contains all special characters, you can configure it to replace the special characters with a separator or the first child topic’s name in the URL of the AEM Site output.




