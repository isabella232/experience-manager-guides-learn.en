---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, August 2022 release
<<<<<<< Updated upstream
description: Latest release of Adobe Experience Manager Guides as a Cloud Service
exl-id: a01bfe8a-4715-438c-bb94-aa1d31f6662d
=======
description: August release of Adobe Experience Manager Guides as a Cloud Service
>>>>>>> Stashed changes
---
# August release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the August release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.8.167.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the August release of AEM Guides as a Cloud Service.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service August 2022 release. 

### FrameMaker and FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Not compatible | 2020 Update 4 and above |
| | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | 
| --- | --- | --- |
| 2022.8.0 | 2.7.5 | 2.7.5 | 
|  |  |  |  


## New features and enhancements

AEM Guides as a Cloud Service provides many enhancements and new features in the August release:

### Layout view in the Map Editor

Now you can view the complete layout of a DITA map in the Map Editor. When you open a map for editing, it opens the **Layout** view of the Map Editor. In this view, you can see the map hierarchy in a tree view and also organize or structure the topics in a map. 

![layout view](assets/layout-view-map.png)

The Layout view contains a separate tool bar which helps you perform many tasks on the topics present in a map. 
You can insert topic references, topic group, key definitions in a map. You can reorganize the topics present in a map by moving them up, down, left, or right. You can also drag-and-drop the topics to move them in a map. The Map Editor also provides the icons to  lock or unlock files, check the version history, and do a version label management. 


The Layout view also provides the **View Options** to show or hide line number, show or hide check box, or show the file name or title  for the topics in a map.


![view-options](assets/view-options.png)

You can also view the topics based on the conditional filters applied on them.

In addition to organizing topics in the map file, you can also add, move, copy, paste, or delete references using the **Options** menu available for an element in the Layout view. You can also drag-and-drop a topic or a map from the repository panel to the map opened in the Map Editor.

The right panel displays the Content Properties and the Map Properties in the Layout view of the Map Editor. The Inline Attributes defined for the selected topic are displayed against the topic in the Layout view. For example, you can quickly find all topics which have the platform attribute defined as `IOS`.

Now you can also set the metadata information for the topics or the map. You can define the Nav Title, Link Text, Short Description, and Keywords for the selected topic or map. 

![layout view right panel](assets/layout-inline-attributes.png)

For more details, see *Layout view* section in Using Adobe Experience Manager Guides as a Cloud Service.

### Inline Attributes in the Editor Settings

AEM Guides now allows the configuration of **Inline Attributes** by your administrator from the **Editor Settings**. You can also add new inline attributes or delete the existing ones from the **Inline Attributes** tab in the Editor Settings. 
The configured Inline Attributes defined for a topic are displayed against the topic in the Layout view. 

![Editor Settings](assets/editor-settings-inline-attributes.png)


### Additional Filters in the Repository view

Now the filter search in the repository view has been made more powerful. Two new search criteria, **Last Modified** and **Tags** have been added to filter the files and to narrow down your search in the AEM repository:
* **Last Modified**: You can look for files that have been last modified after a selected date but before a selected date. You also have the option to use the predefined criteria  and look for files that have been last modified in the last 2 hours, last week, last month, or last year.
* **Tags**: You can also look for files that have specific tags applied on them. You can either type the tag or select it from the dropdown list.
 
![Repository view filters](assets/repo-filter-search.png)


## Fixed issues

The bugs fixed in various areas are listed below:

* Deprecated Lucene index is used in  /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java  (9291)
* Updated Node.js is not used for publishing. (9835) 
* DITA topic is not updated automatically with the changes done on the **Properties** page. (8745)
* Frontmatter element when added to a DITA bookmap does not function correctly. (9507)
* Native PDF | A blank PDF is generated on using **Quick Generate** for multiple files when an empty element is selected. (9822)
* Native PDF | Appendix is published as a chapter in the PDF output. (9829) 
* Native PDF | When an SVG image is edited, it is not shown updated in the page layout. (9069)
* A regular hyphen character is inserted when a `Nonbreaking Hyphen` character is inserted using the **Insert Special Character** dialog. (8919)
* XML Editor does not show updated images in the topics if they have been edited. (9500)
* While publishing the output via the Editor, the presets cannot be deleted from the **Output** tab. (9100)
* The sub-maps of a DITA map are not checked out using the **Select All** option from the ellipsis menu. (9814)
* Unable to drag-drop map or topic templates from the **Templates** menu to the custom map template in the Web editor. (9846)
* Unable to create a new topic or map template in the sub-folder of a map or topic template. (9888)
* No option is present to browse the topics or maps present inside the sub-folders of a map or topic template. (9889)
* When a Schematron file is updated and saved along with the DITA file the right panel is not displayed (if the DITA file breaks the validations present in the Schematron file). (9986)
* A new duplicate output preset can be created if its name is the same as an existing preset. (9997)
* SVG images get corrupted and do not publish correctly on generating the HTML output. (9949)


## Known issues

Adobe has identified the following known issues for AEM Guides as a Cloud Service August 2022 release.

### Known issues with workaround

Use the given workaround for the following known issues:

* The Layout view is not visible in the Map Editor.

  **Workaround**: Update the ui_config.json in the Folder Profile.

* Symbols.json is overridden so issue 8919 occurs.

    **Workaround**: Updated symbols.json must be merged with overridden symbols.json.

### Other known issues

* If multiple files are selected from the result section displayed on performing a search on repository and then drag-dropped in the author view, only a single file gets added.
