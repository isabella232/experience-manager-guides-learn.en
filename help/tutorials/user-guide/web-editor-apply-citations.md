---
title: Add and manage citations in your content
description: Learn how to apply, import, manage, filter, search, change citation style, edit, preview, insert, delete, and generate content output with citations in AEM Guides.
---

# Add and manage citations in your content

Citations are references to the source of information added to your content. Using citations, you can credit the authors of the source information and help readers to follow up on the source information. Adding citations makes your content more reliable and prevents plagiarism. They also allow you to display well-researched content.

In AEM Guides, you can add and import citations and apply them to your content. You can add these citations from any source of books, websites, and journals. 


AEM Guides helps you to edit, preview, and sort your citations. After adding your citations into the content, you can generate the output using Native PDF. You can also add the bibliography or references page in the Native PDF output. 

AEM Guides supports multiple styles of citations, such as Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE), and American Heart Association (AHA). The recommendation is to use them clearly and consistently. 


>[!NOTE]
>
>Currently AEM Guides only supports Native PDF for citations.


## Add citations 

To add citations, follow these steps:

1. Select the **Citations** ![citations icon](images/citations-icon.svg) icon in the left panel.
The **Citations** panel opens.

    ![](images/citation-panel.png){width="300" align="left"}

1. In the **Citations** panel, select ![Add icon](images/Add_icon.svg). From the dropdown you can choose to add a new citation or to import  a citation.

1. Select **New Citation** to add a new citation.
The **Add Citation** dialog box opens.

    ![citation panel in the web editor](images/citation-add.png) {width="300" align="left"}


1. Fill in the fields in the **Add Citation** dialog box.

    >[!NOTE]
    >
    >You can also add the ISBN or DOI or PubMed ID. AEM Guides populates the other fields automatically. 

    | Book | Website |Journal|
    | --- | ---|---|
    |**Source** <br> From the drop-down, select the source of the citation as a Book.| **Source**<br>From the drop-down, select the source of the citation as a Website.| **Source** <br> From the drop-down, select the source of the citation as a Journal.|
    |**Search by** <br> Select **ISBN** or **DOI** from the drop-down to search for the digital ID linked to the citation.  <br> DOI: Digital Object Identifier <br> ISBN: Unique Numeric Book Identifier | **Search by** <br> Select **DOI** from the drop-down to search for the digital ID linked to the citation.  | **Search by** <br> Select **DOI** or PubMed ID from the drop-down to search for the digital ID linked to the citation. <br>  <br> |
    |**Author** <br> Add the first and last name of the author of the citation. Select ![](images/Add_icon.svg) to add more names. | **Author** <br> Add the first and last name of the author of the citation. Select ![](images/Add_icon.svg)  to add more names. | **Author** <br> Add the first and last name of the author of the citation. Select ![](images/Add_icon.svg)to add more names. | 
    |**Title** <br> Add the title of the book. | **Title** <br> Add the title of the web page.| **Title** <br> Add the title of the article.| 
    |**Editor** <br> Add the editor of the book. | **Website Name** <br> Add the name of the website. | **Journal Title** <br> Add the title of the work in which the article is found.| 
    |**Edition** <br> Add the edition of the book.| **URL** <br> Add the web link of the website to browse the content.| **Year** <br> Add the year in which the article is published. |
    |**City** <br> Add the city of the publication.| **Accessed Date**<br> Add the date on which the content of the website is accessed. | **Volume** <br> Add the volume of the work in the series. |
    |**Publisher** <br> Add the name of the publisher of the book. | **Published Date** <br> Add the date on which the content of the website is published.|**Number** <br> Add the number of the volume within the series. |
    | **Year** <br> Add the year in which the book is published.|**Updated Date** <br> Add the date on which the content of the website is updated.| **Pages** <br> Add the page number or page range in which the article is found. |
    | **Version** <br> Add the version of the book.| **Unique ID** <br> Add a unique ID for the citation. A Unique ID is a unique identifier for that citation.| **URL** <br>Add the web link to the journal. |
    |**Series** <br>Add the series of the book. || **Unique ID** <br> Add a unique ID for the citation.A Unique ID is a unique identifier for that citation.|
    | **URL**  <br>  Add the web link to the book.| 
    | **Unique ID** <br> Add a unique ID for the citation. A Unique ID is a unique identifier for that citation.|

 

 

1. Select **Done**.

    A new citation is added to the Citation panel.

>[!NOTE]
>
> Adding a Unique ID for the citation field is mandatory.  You cannot change the unique ID once the citation is added.

## Import citations 

To import citations, follow these steps:

1. In the left panel, select **Citations** ![citations icon](images/citations-icon.svg).

    The **Citations** panel opens.

1. In the **Citations** panel, select ![Add icon](images/Add_icon.svg), and then select **Import** from the dropdown.
1. Browse a .bib file from your system and import it .

    >[!TIP]
    >
    > A .bib filename extension is a BibTeX Bibliographical Database file. It's a specially formatted text file that lists references about a particular source of information.
    
    Once the file is imported successfully, you can view the references in the citations panel.

    >[!NOTE]
    > <ol><li> AEM Guides imports only those citations which are unique and not already present.
    > <li> AEM Guides can import citations from a Book, Journal, or a Website. Currently it does not support citations from other sources.
 
## Manage citations

The citations are sorted alphabetically in the left panel. Search for the citations according to the sources to use in your topic.

### Filter

Select the **Filter** ![](images/filter-search-icon.svg) icon next to the search bar and select the source options from the drop-down to filter the citation list. It allows both single and multiple selections. 

* **All Sources**: It shows a complete list of citations, including all the sources.

* **Book**: It shows the list of citations sourced from books.

* **Website**: It shows the list of citations sourced from websites.

* **Journal**: It shows the list of citations sourced from journals.

### Search

Search the citation for your content.

1. In the left panel, select Citations.
The **Citations** panel opens.

1. Use the Search bar to search for the appropriate citation from a long list.

### Change citation style {#change-citation-style}

Your system administrator can change the style of citations from the **Citations**  dropdown in the **General Settings** tab in the **Editor Settings**. 
These styles determine the way how citations appear in the preview pane or the Native PDF output.

The following options are available in the dropdown:

|MLA |APA| Chicago | IEEE | AHA|
|---|---|---|---|---|
|Modern Language Association Style <br> | American Psychological Association Style| Chicago Manual of Style| Institute for Electrical and Electronics Engineers Style| American Heart Association Style|
| Example:<br> Crawford, Claire, et al. *Emotional Content of Dark Memories*.Edited by Memory, vol 16, 2010, Amsterdam.| Example: <br> Crawford, C., J., & , C. (2010). *Emotional Content of Dark Memories* (505-16 ed.). 10.1080/ 09658210902067289| Example: <br> Crawford, Claire, et al. *Emotional Content of Dark Memories*. 505-16, 2010. |Example: <br> C. Crawford, J. , and C. , *Emotional Content of Dark Memories*. Amsterdam, 2010. | Example: <br> C. Crawford, J. , and C. , *Emotional Content of Dark Memories*. Amsterdam, 2010.|


## Edit a citation

To edit the citation, follow these steps:

1. Hover over the name of the citation from the list. Select  ![](images/options.svg) the **Options** icon.

1. Select  **Edit**.

The **Edit Citation** dialog box opens.

1. Make the required changes. Select **Done**.
The selected citation is edited.

>[!NOTE] 
>
>You cannot change the unique ID once the citation is added.

## Preview a citation 

To preview a citation, follow these steps:

Hover over the name of the citation from the list. Select     ![](images/options.svg) **Options** icon.

1. Select **Preview**.
You can preview the content and format of the citation in the preview pane.

    >[!NOTE]
    >
    >The preview is based on the citation style that your administrator has selected in the **Editor Settings**.

1. Click anywhere on the screen to close the preview box.

    ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]  
>
> You can also preview a citation inserted in a topic from the Assets UI or the Preview tab of the Web Editor.

## Insert citations

Perform the following steps to insert citations to a topic:
 1. Select the topic in the repository panel, then double-click to open it in the editing window. 
 1. Put the cursor at the location of the topic where you want to add the citation.



You can insert citations to the topic from the main toolbar or the left panel.

### From the main toolbar 

1. Select the **Citations** ![citations icon ](images/citations-icon.svg) icon in the main toolbar. 
1. In the **Citations** dialog, choose the citation. You can also select multiple citations. 
 ![citation dialog](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. You can filter citations by typing the first few alphabets in the search panel of the **Citation** dialog box.

1. Click **Done**. 
 The selected citation is added at the cursor location in your topic. 
 

### From the left panel

>[!NOTE]
> 
>To view the **Citations** icon from the left panel, your system administrator must select the **Citations** option in the **Panels** tab in **Editor Settings**.

1. Select **Citations** ![citations icon ](images/citations-icon.svg) icon in the left panel. 
1. Drag the citation from the **Citations** panel and drop it at the appropriate location in the topic.  
    
    You can also select **Insert** from  ![](images/options.svg) **Options** to insert a citation. 

    ![insert citations](images/citation-panel-insert.png)
1. To select multiple citations, right-click a citation in the topic and select **Modify Citation** from the shortcut menu. 
1. Select the citations that you want to insert from the **Citation** dialog.
1. Select **Done** to add them to the topic.  

Once you have inserted citations in the topic, you can preview them in the Web Editor. You can also publish content with citations using Native PDF. 



## Delete a citation

You can delete a citations from the Citaitons panel or from a topic where you have inserted.

### Delete a Citation from Citations panel

To delete a citation from the Citations panel, follow these steps:

1. Hover over the name of the citation from the list. 
1. Select the ![](images/options.svg) **Options** icon.
1. Select the   **Delete** ![](images/Delete_icon.svg).
The confirmation dialog box opens.
1. Select **Yes**.
The selected citation is deleted from the citations panel.



### Delete a Citation from a Topic

To delete a citation that is already used in the topic, follow these steps:

In the topic, place your cursor at the end of the citation.

1. Right-click a citation in the topic and select **Modify Citation** from the shortcut menu. The Citation dialog opens.
![shortcut menu of a citation](./images/modify-citation.png)

1. You can choose the citations you want to insert into the document.

    >[!NOTE]
    >
    >The citations that are already used in the topic are replaced with the ciations that you select from the dialog.


1. Select **Done**.

## Generate output of content with citations

Once you have inserted citations in the topic, you can publish content with citations using Native PDF. 

In the Native PDF output, the citations appear within the content where you have inserted them. You can also create a Bibliography page. When you click any citation, you are redirected to the bibliography page.

Create a **Citations** page layout in the PDF templates, and include it in your document. All the citations used in the book get listed on one page that appears in the PDF output. To learn more about creating a page layout, view [Create a page layout](../native-pdf/components-pdf-template.md#create-page-layout).


To change the view and feel of the citation page, view [Customize PDF templates](../native-pdf/pdf-template.md).



### Apply content style to a citation

Apply formatting to the citation when added to the topic. 

1. Select **Stylesheets** in the **Templates** panel of a Native PDF output preset.   It opens the **STYLES** panel that contains all the styling options. 

1. In the Search panel, search for `<cite>`.

To learn more about styles, view [Work with the common content styles](../native-pdf/stylesheet.md).