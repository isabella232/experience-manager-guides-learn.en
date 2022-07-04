---
title: Native PDF Publish Feature | Components of a PDF template
description: Learn the various components of a PDF tempalte and how to customize and configure them.

---
# Components of a PDF template

A PDF template has four components: Page Layouts, Stylesheets, Resources, and Settings. You can create a template by customizing these individual components and associating the template with an output preset while generating a PDF output. The following sections cover these components and their customization process in detail.


## Create and customize page layouts

Settings in the Page Layouts component allow you to design the structure of a page by defining the header, footer, and content area on a page. Using the WYSIWYG page layout editor, you can create a page layout for different sections in a PDF, such as the front and back cover pages, chapter, Table of
Contents (TOC), index, blank page, List of Figures (LOF), List of Tables (LOT), glossary, or create a layout for a custom page. In the PDF template Settings, you can assign a page layout with different topics in a DITA map, which are then used to generate the PDF output.  

### Create a new page layout
> **Note**: There are 2 page layouts that are shipped out of the box - Common and TOC. You can customize these or create new page layouts.

1. In the Web Editor, go to the **Output** tab.
1. Expand the left sidebar and click on **Templates**.
1. Open the template that you want to work with.
   > **Note**: You can open a template by double-clicking on its name or clicking the > icon next to its name.
1. To create a new page layout, do one of the following:
   * Hover over **Page Layouts** and click the (*Options* icon) **...** and choose **New Page Layout**.
   * In the **Templates** panel, click the **+** icon next to **Templates** and choose **Page Layout** from the context menu.
      
      This opens the Add Layout dialog.
      
      ![Add Layout dialog](assets/add-layout.png)
1. Specify a name for the new page layout.
   > **Note:** Avoid using any special characters when naming a page layout. A space in the name is replaced with an underscore “_”.
1. Click **Done**.
   
   The new layout is created and added under Page Layouts.

### Customize a page layout
1. In the **Templates** section of the template that you want to edit, double-click on **Page Layouts** or click the **>** icon before **Page Layouts**.

   This displays the list of page layouts within the template.
1. To customize any page layout, do one of the following:
   * Double-click on any page layout.
   * Hover over any page layout and click the (*Options* icon) **...** and select **Edit** from the context menu.

   This opens the page layout editor for customization.
1. Once you have made the desired changes, click *Save All* (or `Crl+S`).

   For more information on defining individual layout elements like header, footer, page number, title, and more, see *Work with page layout elements*.

## Use Stylesheets to customize PDF
Settings in the Stylesheets component allow you to style the page layout components and DITA content using the WYSIWYG editor or directly work with the CSS file. You can create your own styles or customize the default style properties. The WYSIWYG editor gives you the access to most of the properties that you would need to style your page layout or DITA content. For advanced customizations, you can work directly in the CSS editor.

### Create a new stylesheet
While CSS files are provided for content and layout, you can create a new stylesheet to apply multiple customizations to a specific style type that can then be applied to a target component. For example, to style a TOC title (`.toc-title`), you can apply a font size of 21 pt in Stylesheet A and a font size of 26 pt in Stylesheet B.

To create a stylesheet, follow the below steps:
1. In the **Templates** panel, do one of the following:
   * Hover over the **Stylesheets** tab and click the (*Options* icon) **...** and choose **New Stylesheet**.
   * Click the **+** icon next to **Templates** and choose **Stylesheet** from the context menu.
   
   This opens the Add Stylesheet dialog.
   
   ![Add Stylesheet](assets/add-stylesheet.png)
1. Specify a name for the new stylesheet.
1. Click **Done**.
   
   A new stylesheet is created and added under the Stylesheets section.

### Create a new style
By default, the CSS files contain styles for heading, paragraph, character, hyperlink, image, table, div, page, and other styles. You can also create new styles under the base styles and apply them to any DITA content or page layout components.

To create a new style, follow the below steps:
1. Right click on any style and choose New Style from the context menu.

   This opens the Add Style dialog.
   
   ![Add new style](assets/add-style.png)
1. <Need info>
2. Click **Done**.

   A new style is created and added under the base style.

### Customize a predefined or new style
Once you have created a new CSS file with default styles or want to customize styles in an existing CSS file, you can use the styles editor to do so.

To customize a style, follow the below steps:
1. Double-click on **Stylesheets** or click the **>** icon before **Stylesheets**.

   This displays the default (Content and Layout) and custom CSS files.
1. Open a stylesheet for editing.
   
   To open stylesheet for editing, do one of the following:
   * Double-click on the stylesheet name.
   * Hover over the stylesheet name and click the (Options icon) ... and choose Edit.
   
   This opens the stylesheet for editing and displays the list of styles in the Styles panel.

   ![Customize style](assets/customize-style.png)

1. To customize a style, double-click on a style or click the > icon before a style to view and customize it using the Styles editor.

## Work with resources
This is a container for all assets used to design a template. You can think of it as a folder, which contains assets such as background images, custom fonts, logos, and more. Whenever you add an asset in your template, it is upload or check in to the asset folder. You can then use these assets to customize or design your PDF templates.

To add an asset file to the Resources folder, follow the below steps:
1. Hover over the Resources folder tab and click the (Options icon) ... and choose Import.

   This opens the Upload Assets dialog.

   ![Upload assets](assets/resources-import-assets.png)
   
   The path where the asset file will be uploaded is shown in the **Select Asset Folder** field.
   > **Note:** You cannot change the path for uploading assets. By default, all assets are stored under the `/content/dam/dita-templates/pdf/<PDF-template-name>` folder.

1. Click **Choose Files** to browse the asset file from your local machine
1. Click **Upload**.
The selected file is imported and listed under the Resources folder.

## Advanced PDF Settings
Use the Settings section to configure the advanced settings for PDF’s page layout, starting PDF from odd or even page, formats for the cross references, and enabling printing marks in the final PDF that's generated
using the template.

To configure, click **Settings** in the **Templates** panel to view the following options:

**Page Layouts**

Use the Page Layouts tab to apply a page layout for a specific page in your PDF. For example, to select a layout for the front cover page, click the dropdown menu under the Cover Page field and select the layout you have designed to generate the cover page.

For more information on page layouts, see *Setting Page Layout*.

**General**

Set the basic configuration settings for starting a chapter from odd or even page, the TOC structure, and define the leader line format for the TOC entries. You can define the following setting:

* **Always start chapter from**: Allows you to define how each chapter is published in the final PDF. You can choose from a **New Page**, **Odd Page**, or **Even Page** options.

* **Start each topic from a new page**: Select to begin each topic from a new page. If you want to keep your chapters in continuation without any page gaps, then deselect this option.

* **TOC Structure**: Allows you to customize the hierarchy of the Table of Contents. It uses the following additional settings:

   * **Use Headings up to Level**: It allows you to adjust the number of heading levels to be displayed in the TOC structure of your PDF.
   * **Readjust heading levels as per the source TOC hierarchy**: Select this option to reset the TOC heading levels as per the DITA map’s chapter or topic heading levels in the PDF output.
   * **Add or replace heading from the source TOC to maintain the hierarchy**: Select to use the navigation title attribute’s heading given to any Chapter or TOC heading levels from the DITA map.
   * **Do not show page number for the first level in TOC**: Select this option to hide the corresponding page numbers for all chapter first-level headings containing nested heading levels.
   * **Leader format**: Use the drop-down to select Dotted, Solid, or Space leader lines to connect heading levels to its corresponding page numbers.

   For applying TOC structure and styling heading levels, see *Define Table of Contents*.
* **Use table continuation marker**: Select this option to define markers for long tables that spread across multiple pages. For more information on using table continuation markers, see Use table continuation markers.

**Print**

Configure the print production settings to assign printer marks, select color models, and specify properties related to printing of your PDF output.

* **Printer Marks**: When you prepare a document for print production, printer marks are added to the page boundaries to assist in proper alignment, trimming, and color selection during printing. By selecting a printer mark, the page boundary is extended to accommodate the mark, which are trimmed during print. You can choose to display the following printer marks in your PDF output:
   * **Trim Marks**: Select the option to place a mark at each corner of the trim area to indicate where the paper needs to be trimmed after printing.
   * **Bleed Marks**: Select to place a mark at each corner of the bleed box to indicate the trim area for the extended image.
   * **Registration Marks**: Select to place a mark outside the crop area for aligning the different separations in a color document.
   * **Color Bars**: Select to add a strip of colors outside the trim area to maintain color consistency and adjust ink density when printing.

   Set dimensions for the selected printer marks using the **Line Width**, **Line Color**, and **Bleed Box Width** options.

* **Media Box size**: This is the overall page size including the extended area occupied by printer marks. Use the drop-down option to select the page size for your PDF output or create your own custom size.

* **Color Space**: The RGB and CMYK color modes are used for mixing color. Choose RGB to display the generated PDF digitally and CMYK for physical printing. Colors defined in the document will be converted to the chosen color space.
   > **Note**: An ICC color profile is necessary for PDF/A creation if using CMYK color space.

   ![ICC Profile](assets/icc-color-space.png)

   For more information on applying these print settings, see *Printing preferences*.

**Cross references**

Use the Cross-reference tab to define how the cross-references are published the PDF. You can format the cross-references for topic title, tables, figures, and more. For more information, see *Format cross-references*.