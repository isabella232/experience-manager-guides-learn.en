---
title: Create and customize Native PDF templates
description: Learn how to Create and customize Native PDF templates.
exl-id: 7660da8e-8a1e-4493-b99b-9b5de9a7483f
---
# PDF template {#PDF-template}

Using a template ensures consistency in content layout and structure. As templates are predefined, you can avoid rework on formatting issues that arise for every new project or updates. Templates enable you to design page layouts, style content, and apply various settings to customize your PDF.

While authors can use the PDF presets to generate output, developers can create their own templates. There are sample factory templates shipped out of the box, which can be further customized or duplicated by the developers as per their organizational requirements.

Expereince Manager Guides supports factory PDF templates and custom PDF templates.

## Factory PDF templates

These are the OOTB templates that you can preview or duplicate to create the custom PDF templates. When you duplicate a factory template, a new custom template is created using it as the base. 

## Custom PDF templates

You can create custom PDF templates in two ways:

* Create a new template by cloning a factory template
* Duplicate an existing factory or custom template


## Create a new PDF template {#create-pdf-template}

You can create custom PDF templates with specific page layouts and define formatting for page layout components (like TOC, index, glossary) or DITA components (like heading, paragraph, list) using stylesheets. You can create a new template from scratch or build it using a sample template. 

To create a new PDF template, perform the following steps:
1. In the Web Editor, go to the **Output** tab.
1. Expand the left sidebar and select **Templates**.
<img src="assets/create-pdf-template.png" alt="Create PDF template" width="400">
1. In the **Templates** panel, select the **+** icon next to **Templates** and choose **PDF Template**.
1. Specify a name for the template in the **New PDF Template** dialog.

   >[!NOTE]
   >
   >  You can also preview a thumbnail image for the template while creating and duplicating a template. Edit or delete the thumbnail image using [**Properties**](#properties-option) in the **Options** menu.
   
1. Click **Create**. 

   The new template is created and added in the **Templates** panel. 

## Duplicate a PDF template {#duplicate-pdf-template}

If you want to create a new template with the same page layouts and formatting as that of an existing template, you can create a copy. Once a template has been duplicated, you can further customize its components as needed.

To duplicate an existing PDF template, follow the below steps:
1. In the Web Editor, go to the **Output** tab.
1. Expand the left sidebar and select **Templates**. This opens the **Templates** panel.
1. Hover over the template that you want to duplicate and select the **...** *Options* icon and choose **Duplicate** from the context menu.

   This opens the **Duplicate PDF Template** dialog.   

   <img src="assets/duplicate-template.png" alt="Duplicate PDF template" width="350">  

   *Preview the template and update the title and the description In the Duplicate PDF Template dialog.* 

1. Specify a name for the template.

   The **Name** field is pre-populated as a copy of the same name as the source template. You'll view an error message if the template with the same title exists.  



1. To specify a preferred name, remove the pre-populated name and specify a name.
1. Click **Duplicate**.
   
   A duplicate template is created and added under the **Templates**.

## Other operations on the templates

You can also perform the following operations on the templates from the **Options** menu:

 <img src="assets/PDF-template-options.png" alt="Duplicate PDF template" width="350">   
 
### Delete

Select the Delete option to delete the selected template. Then, select Yes on the confirmation prompt. 
The preset is removed from the **Templates**.

### Properties{#properties-option}

Select this option to view and edit the properties of the template. You can preview the existing image for the template. You can also edit or delete the Preview image. You can also change the title and description of the template.

### View in Assets UI

Select this option to view the template in the Assets UI. As it opens the root location of the template, you can view all the resources of the template.

Once you have created the custom template, you can choose it from the Page Layouts in the PDF output preset. 
Learn how to [publish a PDF output](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/output-gen/web-editor/native-pdf-web-editor.html?lang=en).

>[!NOTE]
>
>If your folder has a Folder Profile configured on it, then you'll view only those PDF templates that are configured on the Folder Profile.

Based on your setup your administrator can configure the  templates:

<details>
<summary> Cloud Services </summary> 

For details on setting up global and folder-level profiles, view [Configure templates](../cs-install-guide/conf-folder-level.md#id1889D0IL0Y4) section in the Installation and configuration guide for Cloud Services.

</details>

<details>    
<summary>  On-premise Software </summary>

For details on setting up global and folder-level profiles, view [Configure authoring templates](../install-guide/conf-folder-level.md#create-custom-authoring-template-id1917d0eg0hj) section in the On-premise Installation and configuration guide.

</details>

## Customize a PDF template {#customize-pdf-template}

You can customize templates by tweaking the template components and applying style formats using stylesheets.

To customize a PDF template, perform the following steps:
1. In the Web Editor, go to the **Output** tab.
1. Expand the left sidebar and select **Templates**.
   
   This opens the **Templates** panel.
1. To view a template's components, do one of the following:

   * Select the > icon next to a template or double-click the template name.
   * Hover over any template and select the ... (**Options** icon) and choose **Edit** from the context menu.
   
      By default, this opens the **Settings** panel in the templates editor.
   <img src="assets/customize-pdf-template.png" alt="Customize PDF Teamplte" width="350">
   
   >[!NOTE]
   >
   >  Your adminstrator can download the latest templates from the following path and replace the existing ones:
   >
   > `/libs/fmdita/pdf`

   The various template components that you can customize are categorized under the following sections:
   * Page Layouts: A typical PDF contains different pages, such as a front cover or title page, TOC, chapter, index, citations, and more. The Page Layouts section allows you to design the look-and-feel of different pages that would make up your PDF. For more details, view [Page Layouts](../native-pdf/components-pdf-template.md#page-layouts).

      In addition to the appearance, you can also define the arrangement of page elements such as the header, footer, and content areas on a page. To know more on customizing a page's layout, see [Create and customize page layouts](components-pdf-template.md#create-customize-page-layout).

   * Stylesheets: The settings in the Stylesheets section allows you to customize the look and feel of the page layout components like the TOC, index, glossary, citations, and more. In addition, you can also customize the styles for the DITA content like headings, paragraphs, lists, and more. To know more on using the stylesheets, see [Use Stylesheets to customize PDF](components-pdf-template.md#stylesheet-customization).
   * Resources: Store asset files that you would need to customize or design PDF templates. Assets such as logos, custom fonts, background images, and more are stored in the Resources. To know more on utilizing resources, see [Work with resources](components-pdf-template.md#work-with-resources).
   * Settings: Configure the output settings for generating a PDF using the template. This section allows you to define template mapping for various pages in a PDF, chapter starting page, print markers, citations, and more. 
   You can also arrange the order in which they should appear in your final PDF output.
   For more information on applying settings, see [Advanced PDF Settings](components-pdf-template.md#advanced-pdf-settings).
   
      
1. To customize a template component, double-click a template component or select the > icon before it.
   
   For example, double-click *Page Layouts* or select the *>* icon before *Page Layouts* to view the available
page layouts.
1. Once you have made the desired changes, select *Save All* (or `Ctrl+S`).
