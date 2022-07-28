---
title: Native PDF Publish Feature | Design a page layout
description: Learn how to design your page layout for presenting information in different sections of your PDF output. 
hide: yes
hidefromtoc: yes
---

# Design a page layout

When creating a PDF document, you would have different sections for presenting different types of information. For example, a PDF document would start from a front or cover page, which would have your company&#39;s logo, book title, or version information. Then there would be chapters, appendices, or glossary pages. Each section in a PDF document looks different and that is achieved by creating and customizing the page layout.

When you design your page layout, you can define the various elements that make up a page. For example, you can define the page size, margins, header and footer, orientation, and other page specifications on a page. The Native PDF Publishing feature allows you to design your page as per the CSS Paged Media standards. Most of the settings that are covered under the CSS Paged Media can be easily customized using the Native PDF feature&#39;s user interface. For some other advanced-level formatting, you can use the Source view to write your own CSS code.

Once you have designed the page layouts, you need to associate these layouts with their respective sections in the PDF Page Layout settings. See the _Create and customize page layouts_ section for details on how to create and open a page layout for customization.

## Types of page layouts and their variants

A PDF document typically contains the following sections:

* Cover page
* Table of contents
* Lift of figures
* Lift of tables
* Chapter or topic pages
* Glossary
* Index
* Back page

These sections would need a corresponding page layout to present the information in a specific format. In addition, you can also have a blank page that is used as a filler to start a new chapter from an odd or even page. In that case, you would need a blank page layout.

The Page Layouts settings under the **Template > Settings** section allow you to define which template is to be used for different sections of your PDF. Each page layout can further have different first, right, or left page combinations. These are governed by the rules defined under the *CSS Page Media* standards.

## Create the first, right, or left page layouts

Different page layouts in your PDF template can be further customized by having different first, right, or left page layouts. You can design these pages differently using the page layout designer.

>[!NOTE]
>
>If you want to have a single page layout for a section in your book, then you do not need to create the First, Right, or left page layouts.


Consider the following points when creating the page layouts:

* If you want to use a single page layout for all pages within a chapter, then you would create only a single Chapter page layout.
* If you want to have a different look and feel for the first page for chapters in your book, then you need to create a First page layout for your chapters.
* If you want to have a different look and feel for every left and right side page of your book, then you need to create the Left and Right side variants for your chapter page layout.
* If you want your chapters to start from an odd or even page, then you will need to create a Blank page layout. This page layout is used to fill the gap between two chapters to ensure the chapter starts from the desired odd or even page.

The following example will walk you through the process of creating variants of a page layout:

1. Create a "Chapter" page layout using the steps given under *Create a new page layout* procedure.

    A blank Chapter page layout is created and added under the Page Layouts.

    By default, when you create a page layout, it is also opened up for editing. The following screenshot displays a blank (default) page layout:

    <img src="./assets/default-blank-page-layout.png" width="300">

    The header, footer, and content area in a template is created by default. You can easily customize these areas using the tools, page properties, and content properties given in the user interface. For advanced configuration, you can use the Source view and add your custom HTML and CSS code.

1. To create a variant for the Chapter page layout:
    
    1. Mouse hover over the **Chapter** layout, and click **Options** to display the context menu.

    1. Click or mouse hover over **Add Layout Variant** and choose the desired page layout (First, Left, or Right) that you want to create.

    The selected page layout is created using a copy of the base Chapter layout. This means that if you have made any changes in the default Chapter page layout, the same changes are replicated in the variant page layout.

## Work with images in a page layout

Based on your requirements, you might want to add an image that appears on every first page of a Chapter (PDF) output. The <u>**Add Image**</u> tool in the page layout editor is used to insert images in a page layout.

For example, if you want to insert an image in the header area of the First page of your chapter output, then perform the following steps:

1. Open the required page layout for editing.

    >[!NOTE]
    >
    >See _Customize a page layout_ section for opening a page layout for customization or editing.

1. Click the Edit Header (<img src="./assets/header-icon.svg" width="25">) icon to bring your cursor in the header area.

1. Click the Inert Image (<img src="./assets/insert-image-icon.svg" width="25">) icon.

    The Select Path pop-up appears.

1. Browse to the image location and click Select to insert it in the header area.

    The following screenshot shows a sample image added in the header area.

    <img src="./assets/image-in-header-area.png" width="500">

    Once an image is inserted, you can modify its attributes to give it the look and feel that you want. The easiest way of changing the way an image or any other element on your page layout looks, use the Content Properties panel to do so. See _Work with Content Properties panel_ for the various properties that are available through the UI to customize.

## Work with fields

Fields are very useful when you want to insert a piece of information that is pre-defined. For example, you can include a Chapter Title field in your chapter's header area that is replaced with the actual chapter's title when published.

There are the following categories for fields that you can insert in your page layout:

* Date
* Time
* Topic Title
* Project Title
* Page Number
* Total Page
* Chapter Title
* Chapter Number
* Metadata

Each of these field categories contain different variations in which the field information can be inserted. For example, a Date field can have different variations such as `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` and so on.

In the following example, we will insert a page number and a topic title in the footer area of our page layout.

1. Open the required page layout for editing.

    >[!NOTE]
    >
    >See _Customize a page layout_ section for opening a page layout for customization or editing.

1. Click the Edit Footer (![](./assets/footer-icon.svg)) icon to bring your cursor in the footer area.

1. Insert a paragraph element by clicking the Insert HTML Elements <img src="./assets/insert-html-element-2.svg" width=25> icon, and selecting Paragraph from the list of elements.

1. Click the Insert Fields ( ![](./assets/insert-fields-icon.svg)) icon.

    The Fields pop-up appears.

1. Select the **Page Number** category from the Field list, the **default(1)** page number format from the Format list, and click **Insert**.

    <img src="./assets/insert-page-number-field.svg" width="400">
    
    <img src="./assets/transparent-background.png" width="70">
    
    >[!NOTE]
    >
    >You can also edit the format of all fields, except the default format. To do so, click the Edit icon next to the format that you want to edit, make changes, and click OK.

    The default page number field is inserted in the footer area of the page layout.

    <img src="./assets/page-number-field-in-footer.png" width="400">

    The top breadcrumb lists the elements in which the information is stored.

1. Enter a blank space after the page number field and click the **Insert Fields** icon.

1. Select the **Topic Title** category from the Field list, the **Chapter.ptl** title format from the Format list, and click Insert.

    The `Chapter.ptl` field, which is populated with the topic's title at the time of publishing, is inserted in the footer area. At this time, the page number and topic title fields are separated by a space.

    <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. To right-align the Topic title, perform the following steps:
  
    1. Click on the Field element on the breadcrumb to select the topic title field.

    1. In the right panel, click HTML Content Properties.

        <img src="./assets/right-pane-content-properties.png" width="350">

    1. Expand the **Layout** properties section, and set the **Float** property value to **right**.

        <img src="./assets/float-prop-html-content.png" width="350">

        The topic title field is aligned towards the right side of the page footer.

        <img src="./assets/topic-title-moved-right-footer.png" width="500">

| _Developer Corner_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

If you like to work directly with the CSS and HTML code, then you can also achieve this by going to the Source view of the page layout and making changes in the code. The following code snippet shows the same footer setting done through the code: 

```md
…
<div data-region="footer">
	<p>
		<span data-field="page-number" data-format="default">1</span>
		<span data-field="title" data-format="default" style="float: right">Chapter.plt</span>
	</p>
</div>
…
```

## Add a chapter TOC

A chapter or a mini table of contents serves as a quick reference for the readers to know what is in the chapter. Typically, a chapter TOC is added at the very beginning of a chapter. So, if you want to use a chapter TOC, then you can add it to the main chapter page layout or the First page layout of a chapter.

In the following example, we will insert a chapter TOC in First page layout of a chapter:

1. Open the required page layout for editing.

    >[!NOTE]
    >
    >See _Customize a page layout_ section for opening a page layout for customization or editing.

1. Place the cursor in the content area of the page layout.
1. Click the Chapter TOC (<img src="./assets/chapter-toc-icon.svg">) icon.

    The default chapter TOC is inserted in the content area.

    <img src="./assets/chapter-toc-default.png" width="400">
    <img src="./assets/transparent-background.png" width="70">
    
    >[!NOTE]
    >
    >The default chapter TOC contains headings 1 to 4. Here, Heading 1 is the Chapter Title itself. So, you may not want to have the chapter title again in the TOC or you may want to increase the level of headings that you want in the TOC. You can customize the TOC by changing the properties.

1. Open the HTML Content Properties panel to customize the TOC heading levels.

    For example, if you want to start from Heading 2, then change the first drop-down list to start from 2.

    <img src="./assets/customize-chapter-toc.png" width="400">

    Similarly, if you want to have headings up till level 5, then change the second drop-down list to 5. The updated TOC will look as shown below:

    <img src="./assets/chapter-toc-updated.png" width="400">

    <img src="./assets/transparent-background.png" width="70">
    
    >[!NOTE]
    >
    >The final published PDF will only show the TOC entries based on the content in your chapters. If you don't have level 5 headings in a chapter, it will not be shown in the final output.

## Work with multi-column page layout

Multi-column page layouts are very common in publishing magazines or indexes in a book. The Native PDF publishing feature allows you to easily split your document into multiple columns. Using different page layouts, you can choose to keep only a specific section divided into multiple columns while keeping the other sections in a single column (or normal) layout.

To create a page layout with multiple columns, perform the following steps:

1. Open the required page layout for editing.

    >[!NOTE]
    >
    >See _Customize a page layout_ section for opening a page layout for customization or editing.

1. As the multi-column layout is applied on the content, excluding the header and footer area, you need to select the content element in the breadcrumb.

    Once you select the content breadcrumb, the HTML Content Properties panel will show the properties for Multiple Columns.

    <img src="./assets/multiple-columns-properties.png" width="400">

1. Use the multiple column properties to customize the multi-column page layout:

    * **Column Count:** Specify the number of columns to divide the page. Use the up and down arrow icons or enter a number to set the number of columns.
   
    * **Column Width:** Specify the width of a column in a multi-column layout. By default, the size is set in pixels (px), you can also specify it in pt, rem, em, %, or in units.

        >[!NOTE]
        >
        >If you don&#39;t specify a size, then the columns are automatically sized to fit in the given page margins.

    * **Column Gap** : Specify the space between individual columns.
  
    * **Column Span** : If you want any element on your page layout to span across columns, then you need to use this property. This is achieved by modifying the style of the desired element using the Stylesheets, for more information see _\<Section explaining style customization>_.

    In your page layout, if you want a certain text to appear on the first page of all chapter page layouts, then you can add it to the First page variant of the Chapter page layout.

    As shown in the following example, the Span Column property for the heading text is set to all. This ensures that even though the document is multi-column, the heading spans across columns.

    <img src="./assets/element-span-across-columns.png" width="400">

    <img src="./assets/transparent-background.png" width="70">
    
    >[!IMPORTANT]
    >
    >You can apply Span Column property to any DITA element.

    * **Column Fill** : Specify how content fills columns. By default, it is set to Balance which fills each column with equal amount of content.

    * **Column Rule** : If you want to have a line in between columns, then use this property to define the line or ruling styles. Specify the values for ruling Style, Color, and Width to add a line in between columns.

## Use Page Properties for different page orientation

While designing a page layout, having control over various page properties is essential. The Native PDF feature encapsulates all major page properties under the Page Properties panel. The Page Properties panel provides access to various properties under the following sections:

* **Page Size**: Specify the page size you want to use for the page layout. The Page Size dropdown list allows you to choose from over 15 page sizes.

* **Orientation**: Specify the page orientation to use for the page layout. You can choose from Portrait or Landscape page orientations. Note that you can choose to have different orientations applied to different page variants in a page layout. For example, you can set Portrait orientation on the First page and Landscape on Left and Right page layouts. 

* **View Rotation**: Specify the view or direction in which the content on the page is laid out. You can choose from Clockwise 90, Anticlockwise 90, or Anticlockwise 180 degrees. This is very useful in a situation wherein you want to use a combination of Portrait and Landscape layouts in your output. For example, you can use portrait as the generic page layout, and you can set landscape page layout for capturing long tables. In that situation, you can choose to display the table content in Clockwise 90 degrees. That way the page will be oriented in landscape and the content will be rotated 90 degrees to maintain continuity in view. We will see how this is achieved as an example later in this section.  

* **Restart Numbering From**: Specify the page number from where the numbering for this page layout will start. For example, you can create a page layout for the Appendix section in your book and set the numbering to restart from 1. 

* **Layout**: Specify page margins along with padding for top, bottom, left, and right sides. 

* **Background**: Include an image as the background image in your page layout. You can specify the height and width of the image along with repetition and position properties. 

* **Footnote**:  Specify the properties to display footnotes in your output. You can choose to specify the margins and padding properties along with a border style. 

Let’s look at an example wherein a combination of portrait and landscape page orientation and view rotation properties are used. In this example, we will create a PDF with default portrait orientation, but a table will be rendered in landscape orientation with content in Clockwise 90 degree view. The final output will look something similar to:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

In the above output, the Contact List information is presented in landscape mode with content also rotated in 90 degrees. The remaining content is displayed in the normal portrait mode.

To achieve this kind of output, we need to perform the following main tasks:

1. Create a page layout with Landscape orientation. 
1. Change the View Rotation property to render content in 90 degrees clockwise direction. 
1. Create a custom style to use the new page layout. 
1. Add the style in the outputcalss definition of the table that we want to render in the landscape page layout. 

Perform the following steps to achieve the above tasks:

1. Create a page layout with Landscape orientation. 
    1. Create a “Landscape” page layout using the steps given under “Create a new page layout” procedure.

    1. In the right panel, click **Page Properties**. 

        <img src="./assets/page-properties-panel.png" width="300">
    1. Change the **Orientation** to **Landscape**. 

1. Change the View Rotation property to render content in 90 degrees clockwise direction. 

    1. Select **Clockwise 90&deg;** from the View Rotation dropdown list. 

    1. Click **Savel All** to save the updated page layout properties.

1. Create a custom style to use the new page layout. 
    1. Expand the left sidebar and double-click on the template in which you want to create the style.

    1. Expand the Stylesheets section. 

    1. Hover over the Layout stylesheet, and click the (_Options_ icon) **…** and choose **Edit**. 
    
        The Layout stylesheet is opened for editing.
    
    1. Right click on **Other Styles** and choose **New Style**.

        <img src="./assets/stylesheet-other-new-style.png" width="300">
    
    1. In the **Add Style** popup, enter `landscape-style` in the **Class** name field.

        <img src="./assets/stylesheet-new-landscape-style.png" width="400">

    1.  Click **Done**. 
        
        A new style named `.landscape-style` is created and added at the end of **Other Styles** list. 
    
    1. Double-click on the `.landscape-style` style to open it for editing. 

    1. Expand the **Pagination** property.

    1. Enter `Landscape` in the **Page Layout** property. 

        <img src="./assets/new-style-with-landscape-layout.png" width="500">

1. Add the style in the outputcalss definition of the table that we want to render in the landscape page layout. 

    1. In the Web Editor, open the file where you want to apply the new page layout. 

    1. Find the `<table>` element, which is to be rendered in Landscape mode. 

    1. In the breadcrumb, click on the `table` element to select the table. 

        <img src="./assets/new-style-table-element.png" width="400">
    
    1. In the right panel, click and open the **Content Properties** panel. 

    1. In the **Content Properties** panel, add a new `outputclass` property with `landscape-style` as property value.

        <img src="./assets/new-style-table-outputclass.png" width="300">
    
    1. Click **Save All** to save the updated file. 

    1. Generate the PDF output. 

The final PDF will have the table content rendered in landscape mode as shown in the beginning of the example. 

## Work with Content Properties panel

The Content Properties panel lets you easily update the look and feel of the elements on your page layout. The properties under the Content Properties panel are divided into the following sections:

>[!NOTE]
>
>For more details about the usage of these properties, see W3C CSS Page Media Standards documentation.

* **Attributes**: Contains ID, Class, and Translate properties. If you set the Translate property to no, then the content in that specific element is not translated.

* **Font**: Contains font-related properties. You can set Font Family, Weight, Size, Text Decoration (as underline, overline, line-through), Text Style (as Bold, Italics, and more), Text Alignment (as left, right, center, or justified), handle White Spaces (as predefine format, no-wrap, break-space, and more), Line Height, Letter Spacing, and Text Indent.

* **Border**: Contains properties to add and format a border to an element in your page layout. You can set Border Side (as all, top, bottom, right, or left), Border Style (as Solid, Dashed, Dotted lines, or more), Border Color, Width, and Radius for having curved border. In the following example, a curved border has been added in the header area of the page.

    <img src="./assets/border-properties.png" width="500">

* **Layout**: Contains properties to configure the layout of an element in your page layout. You can set Height, Width, Margins and Padding (for top, bottom, left, or right), Horizontal or Vertical alignment, Float (as Left, Right, or none), Clear (as left, right, both, or none), element’s Position (as absolute, fixed, relative, or more), Display (as block, content, fix or more), Z Index, Transparency, Transform (by rotating or scaling), and Transform Origin (by X and Y-offset). 

* **Background**: Contains properties to include a background image or color shade. You can set the Image Size (by setting Height or Width), Background Repeat (as repeat, no-repeat, round, or more), and Background Position (as left top, right center, center bottom, or more).    

* **Multiple Columns**: Contains properties to configure multi-column properties for the page or any specific element, such as Chapter TOC. For more details on the properties and how to use them, see _Work with multi-column page layout_. 

