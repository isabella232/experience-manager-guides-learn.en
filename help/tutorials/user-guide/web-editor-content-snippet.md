---
title: Insert a content snippet from your data source
description: Learn how to insert a content snippet from your data source
---

# Insert a content snippet generator from your data source

AEM Guides provides the feature to connect with your data source. You can fetch your data, insert it into your topics, and edit it. You can easily create a content snippet generator and reuse it within your topics. 

Perform the following steps to create a content snippet generator and insert it in your topic:

1. Select **Data Sources** ![](images/data-source-icon.svg)   in the left panel to view the connected data sources. The Data Sources panel opens and displays all the connected data sources. 
 
1. Select a data source to view the content snippet generators available for the selected data source.
![](images/code-snippet-generator.png){width="300" align="left"}
1. Select **Add** to add a new content snippet generator. The **Add content snippet generator** panel opens.

1. Enter the query in the Data query text box.
1. Select the template which maps with your data source from the **Data mapping template** dropdown.
The out-of-the-box templates for the selected data source are displayed in the drop-down. For example, you can view the “sql-table” template for datasource named “PostgreSQL” datasource.

    > [!Note] 
    >  
    > If your administrator has configured customized templates, then you’re also shown those templates in the drop-down list (based on the template path configurations done by your administrator). 
1. Click **Fetch** to fetch the data from the data source and apply the template on the data that results from the SQL query. 
1. You can view the data in the preview or the DITA source view. 
1. The preview shows how the data will be displayed when inserted into the content. The preview displays a small fraction of the data in the format of the selected template. 
For example:
  *	If you’ve selected the sql-table template, you can view the SQL data in a tabular format. 
  *	If you’ve selected the jira-ordered-list template, you can view an ordered list for the Jira issues.
    1.	The source view shows the data in the DITA source view. 
 ![](images/add-content-snippet-generator.png){width="800" align="left"}
    1. To save the results of the query, enter the name of the generator and then click **ADD**.   A new content snippet generator is added to the list.
    >[!NOTE] 
    >
    >You need to follow the file naming convention for the name of the new content generator. You cannot have a space in the name of the content snippet generator. Also, you cannot save a new content generator with the name of an existing content generator. An error occurs.  

## Options for a content snippet generator

Right-click on a content snippet generator to open the Options. Using the options, you can perform the following operations:
* **Insert**: Use this option to insert the selected content snippet generator into the topic opened for editing in the Web Editor. As the data is inserted as a snippet, you can also edit the data within your topic in the Web Editor.

    > [!Note]
    > 
    > Insert option appears only while you are editing a topic.

* **Edit**: Use this option to make changes in the content snippet generator and save it.
* **Delete**: Use this option to delete the selected content snippet generator.
* **Duplicate**: Use this option to create a duplicate or a copy of the selected content snippet generator. The duplicate is created with a suffix (like generator_1) by default. 

### Insert a query snippet

You can also use the **Insert Query Snippet** ![](images/data-source-icon.svg)   from the main toolbar to insert the data snippet into the topics.  You can select a generator from the dropdown, edit your query, or change the template and insert the data in your topic.

![](images/insert-content-snippet.png){width="800" align="left"}
 



