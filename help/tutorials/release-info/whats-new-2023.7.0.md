---
title: Release Notes | What's New in Adobe Experience Manager Guides, July 2023 release
description: Learn the new and enhanced features in July 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# What's new in July 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in version July 2023 version of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see the [Release notes](release-notes-2023.7.0.md) article.

## Map Collection enhancements

A Map Collection helps you organize multiple maps and batch publish them. Many new enhancements have been made to the Map Collection:

- Now, you can also add Native PDF output presets to a map collection and use them to generate the PDF output. 
- You can view the global and folder profile presets created by your administrator and use them to generate the PDF output. 
- Now, you can not only select an individual preset, but you can also enable all the folder profile presets for a DITA map in one go.
![](assets/edit-map-collection.png){width="800" align="left"}   
For more details, view [Use Map Collection for output generation](../user-guide/generate-output-use-map-collection-output-generation.md).

## Review panel to showcase review projects and the active review tasks

Now AEM Guides makes your reviews more seamless. It provides the Reviews panel within the Web Editor. The Reviews panel displays all the review projects and the active review tasks within the review projects that you're part of from the Reviews panel.  
The review panel displays the review tasks in the Author view. You can easily view your review projects and open any active review tasks to view the comments of the various reviewers. As an author, you can quickly address the comments in a topic using the Web Editor. 
![](assets/active-review-task-comments.png){width="800" align="left"} 
For more details, view the **Review** feature description within the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

	
## Connect to a data source and insert data into your topics

AEM Guides provides the feature to connect with your data source.  You can fetch your data, insert it into your topics, and edit it. Connecting to a data source automatically helps you to keep your information updated. This feature is very handy and saves your time and effort.  You can create a content snippet generator for a data source and reuse it within your topics.

>[!NOTE]
>
> Now, AEM Guides allows your administrator to configure the out-of-the-box connectors for JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases. They can also add other connectors by extending the default interfaces.

You can view the configured connectors listed under the Data Sources panel in the Web Editor.
 
![](assets/code-snippet-generator.png){width="300" align="left"}


You can connect to the data source, run a data query, and apply an out-of-the-box template to the results.  You can preview a snapshot of the data that results from the SQL query.   Save the results of the query as a content generator. AEM Guides also allows gives you the options to insert, edit, delete, or duplicate a content snippet generator.
 
Once you have created a content snippet generator, you can reuse it to insert the data into any topics. You can also edit your query or change the template and insert the data in your topic.

![](assets/add-content-snippet-generator.png){width="800" align="left"}
For more details, view [Insert a content snippet from your data source](../user-guide/web-editor-content-snippet.md).



## Add labels while checking in files in the Oxygen Editor

Now you can also add labels to the different versions while checking in a file in the Oxygen Editor. You can add one or more labels (separated by commas) to the same version of a topic. If your administrator has predefined a list of labels, then those labels are displayed as a dropdown. You can choose one or more labels from the dropdown. 

![](assets/oxygen-checkin-dropdown-labels.png){width="300" align="left"}

 

>[!NOTE]
>
> These labels are displayed in the AEM version history of the file. For more details, view Check in a file procedure under the Work with Oxygen Plugin for AEM Guides section.


## Ability to access temporary HTML files while generating the native PDF output

Now AEM Guides allows you to download the temporary HTML files created while generating the native PDF output. In the output preset settings, select the option to download the temporary files.  AEM Guides then allows you to download the temporary files created while generating the output using that preset. 

This features enables better insights into the generation process with access to interim styles and layouts and helps you correct or change your CSS styles according to your requirements. 

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

