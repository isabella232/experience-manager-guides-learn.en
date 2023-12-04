---
title: Native PDF Publish Feature | Work with the common content styles
description: Learn how to create use styleheets and create styles for your content.
---
# Work with the common content styles {#work-with-common-styles}

A stylesheet contains the definitions of styles for the elements that are used in your PDF output. You can choose to work with the sample stylesheets or create new ones. In most cases, creating a copy of the OOTB sample stylesheet will help you get started quickly. 

The styles editor is a WYSIWYG editor that hides all the complexities of a CSS code behind the user interface. Using the style editor, you can easily and very quickly customize the styles for the elements of your choice. The styles are categorized under the following heads:

* Heading Styles
* Paragraph Styles
* Character Styles
* Hyperlink Styles
* Image Styles
* List Styles
* Table Styles
* Div Styles
* Page Styles
* Other Styles

When working with structured DITA content, the style mapping for most of the DITA elements is in place in the default stylesheet. If you are working with standard DITA elements, then you can change their look and feel by directly making changes in the style definition. These style definitions are available under the Other Style category. For more details, see [Work with other styles](#other-styles) later in this topic. 

The following sections cover the most commonly used style settings in the form of examples. 

>[!NOTE]
>
>In the following examples, it is assumed that you are working with the sample stylesheet shipped with the product. 

## Work with Heading Styles {#heading-styles}

The heading styles encapsulate all base styles for the headings used in your content. OOTB you will get 6 base heading styles and a heading style for the topic&#47;chapter and appendix's title heading. In a structured document, the H1 represents the topic's or chapter's title and H2 through H6 are used for sub-topics or sections within a topic&#47;chapter. This hierarchy of headings is automatically applied on your content whenever the corresponding heading is found.  

>[!NOTE]
>
>You can create your own custom heading styles and those can be used in your content using the outputclass. For more details, see Step 4 in [Use page orientation and view rotation](design-page-layout.md#page-orientation-rotation) example. 

### Create custom chapter-level headings {#create-chapter-level-heading}

In a book (or a bookmap), you work with Chapters. The base heading styles are designed in such a way that they get applied on your chapter-level headings without any customizations. However, if you want to create specialized headings for your content, then you will have to create those headings. For example, the default `h1.chapter` heading gets applied on your chapter's title. If you want your chapter title to appear in a different style, then you need to customize the `h1.chapter` style. Similarly, you can create custom styles for sub-headings in your chapter. For example, if you want to create a custom style for all 2<sup>nd</sup> and 3<sup>rd</sup> level headings in your chapter, then you need to create a new style as `h2.chatper` and `h3.chatper`.

As the Native PDF Publishing feature contains the base style definitions for the most common styles, even if you accidentally delete a style, the default style is applied on the content. For example, if there's no style definition for h2 style in your stylesheet, the Native PDF Publishing feature will apply some base style on h2 content. 

In this example, we will create a 2nd level chapter heading style:

1. Open the required stylesheet for editing. 
   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand the **Heading Styles**. 
1. Right-click on **Heading Styles** style and choose **New Style**. 
1. In the *Add Style* dialog, keep the **Tag** name as `h2` and enter `chapter` in the **Class** name field.
1. Click **Done**. 

A new heading style named `h2.chapter` is created and added under the Heading Styles list.  

Once you have created a style, you can customize the required properties of the style using the style editor. 

### Create auto-number headings {#auto-number-heading}

One of the most commonly used output styles is autonumbered headings. These headings represent the chapter number, topic and sub-topic numbers. The auto-number headings are different from the list styles where a list of items within a topic are assigned auto-numbers.  

In this example, we will customize the headings from level 1 to level 3 to use auto-numbers in different formats.

1. Open the required stylesheet for editing. 

   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand the **Heading Styles**. 

1. Select the **h1** style from the list. 
   The properties for the h1 style are shown in the Properties panel along with its Preview. 

   >[!NOTE]
   >
   >The Preview panel gives you a real-time view of any style updates that you apply on any element.  

1. Select the **Autonumber** property. 

   The styles that you can apply on the auto-number list are shown below the Autonumber property. 

1. Set the following properties:
   * **Style**: Select from a wide range of locale-specific or generic numbering styles. You can choose styles like Arabic-Indic, Devanagari, Georgian, Decimal, Lower-Alpha, and more. For the current example, select `upper-alpha`. 
   
   * **Format**: The default format is set to `<x>`, wherein the `x` value is replaced with the numbering Style that you selected in the Style property. For example, if you have selected `decimal` (1) style, then the value of `x` auto-increments for every instance of the `h1` style and goes as 2, 3, and so on. You can also add custom text in the field to format the heading style. For example, if you want all h1 headings to have a prefix of `Chapter`, then you need to set this field as `Chapter <x>`. 
   
   * **Insert Character**: If you want to add any special character in the Format, then click the Insert Character (<img src="./assets/insert-chars.png" width=25>) icon. Select the desired character that you want to add in the style format and click Insert. There are different types of special characters that you can choose from the Select Category drop-down list. For our example, select the Right-Pointing Double Angle Quotation Mark from the Punctuation category.

      <img src="./assets/insert-special-chars.png" width=400>


   * **Start Numbering From**: If you want the numbering to start from a specific number, then provide that value. For our example, keep the default value of 1.

   * **Indent**: If you want to indent the heading, then you need to set the Indent value. For our example, set it to 0 px.

      >[!NOTE]
      >
      >You can enter the value in px (pixels), pt (points), rem, em, &#37; (percentage), or in (inches) units.

   * **Prefix Width**: This is the area that is occupied by the auto-number format. It is automatically set to a size that can easily accommodate the selected style format. If you want to increase the size, then you can replace the default value. 

      When setting this value manually, try changing the other properties that will have an impact on the width. For example, change the font size, the format with prefix (Chapter) or a suffix (:), set the maximum value in the *Start Numbering From* property, and the various font properties to come up with the optimal size.  

      For our example, keep the default value.

   * **Spacing**: Specify the horizontal and vertical spacing. For our example, keep the default values. 

      With the above customizations, the style is customized as shown below:

      <img src="./assets/h1-style-custmization.png" width=500>

   * **Apply Formatting To**: The properties under the Autonumber category will help you define the numbering style. To apply further customizations to the numbering style or the content of your heading format, you can choose Numbering or Paragraph in this field. If you choose Numbering, then any changes to Font, Border, Layout, and other categories will be applied only to the numbering style in the heading. However, if you choose Paragraph, then the changes will be applied on the heading content and not the numbering style. 

   Use the following settings to generate an output shown in the following screenshot:

   |**Heading Style**|**Property**|**Value**|**Additional Comments**|
   | :- | :- | :- | :- |
   |h1|Style|Decimal|These properties are under the Autonumber category |
   ||Format|`Capter <x>:`||
   ||Prefix Width|160 px||
   ||Font &gt; Text Alignment|Left|Make sure that Apply Formatting To is set to Numbering|
   |h2|Style|Decimal|These properties are under the Autonumber category |
   ||Format|`Section <x>:`||
   ||Prefix Width|125 px||
   ||Font > Text Alignment|Left|Make sure that Apply Formatting To is set to Numbering|
   |h3|Style|Decimal|These properties are under the Autonumber category |
   ||Insert Level|2||
   ||Format|`Section <2>.<x>:`||
   ||Prefix Width|125 px||
   ||Font &gt; Text Alignment|Left|Make sure that Apply Formatting To is set to Numbering|
   ||

   <img src="./assets/auto-number-output.png" width=500>

## Work with Paragraph Styles {#paragraph-style}

A paragraph style can be created to apply special formatting on an entire paragraph. However, using the pseudo-class, you can apply a style to only a specific part of the text. In the following example, we will create a paragraph style to use the drop cap style.

### Create the drop cap style {#drop-cap-style}

A drop cap (or dropped capital) style is used in magazines, and literary documents wherein the first character of a paragraph or section is given some special styling. You can achieve the same effect using the Native PDF Publishing feature. 

In the following example, we will create a drop cap style:

1. Open the required stylesheet for editing. 

   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand the **Paragraph Styles**.

1. Right-click on the **Paragraph Style** and choose **New Style**. 

1. In the *Add Style* dialog, keep the **Tag** name as p and in the **Pseudo** **Class** field, select `::first-letter`.

1. Click **Done**. 

   A new paragraph style named `::first-letter`  is created and added under the **Paragraph Styles** list. 

1. Select `::first-letter` under the p style, and set the following properties:
   
   * **Font**: Set the desired font for the first letter in your paragraph. For our example, set the Font Family to cursive, font weight to 500, font size to 30 pt, and choose a font color.
   
   * **Layout**: Set the vertical alignment of the text around the drop cap style. For our example, we will set the Vertical Alignment to Bottom.  

As the `p` tag is mapped with the `<p>` element in DITA, you don't need to explicitly add this style using the outputclass attribute. Wherever in your content a `<p>` element is used, the drop cap style is automatically applied on it. In the following screenshot, the chapter title, short description, and definition list elements have not been formatted with the drop cap style. Only the paragraph style is formatted with the drop cap style:

<img src="./assets/char-style-drop-cap.png" width=500>

## Work with Character Styles {#char-style}

Using the character styles, you can create styles for formatting characters or words within your content. For example, you can create a character style for inline code or filename, or you can create a style that uses multiple styling formats on selected content. 

### Create an inline character style {#inline-char-style}

Formatting inline characters or words in a paragraph is a very common style. The process of creating an inline style involves two tasks – first, create a new style in the stylesheet, and second apply the style in your content using the `outputclass` attribute. 

In the following example, we will create an inline character style:

1. Open the required stylesheet for editing. 

   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand the **Character Styles**.

1. Right-click on the **Character Style** and choose **New Style**. 

1. In the Add Style dialog, keep the **Tag** name as span and enter `BoldItalic` in the **Class** name field.

   <img src="./assets/create-char-style.png" width=400>

1. Click **Done**. 

   A new character style named code is created and added under the Character Styles list. 

1. Select `span.BoldItalic` from the **Character Style** list, and set the following properties:
   
   * **Font**: All font-related properties can be customized from this section. By default, there are some fonts bundled with the product. You can choose the desired font for the character style. For our example, set the Font Family to *Serif,* and select *Bold* and *Italic* in the Font Style property. You can also customize other font properties such as Font Weight (like bold, lighter), Text Decoration (like underline, overline), Font Size, Font Color, Text Alignment, and more.  

      >[!NOTE]
      >
      >You can also add fonts to your template, which are stored in the Resources section of your template. For more details about adding fonts and working with Resources, see [Work with resources](components-pdf-template.md#work-with-resources). 

   * **Layout**: You can set the layout-related properties such as Height and Width, Margin, Padding, Alignment, and more.

   * **Background**: The Background properties allow you to format the background color of a particular style. You can define the background color or image for any style.  

Once you have created the inline character style, you need to apply it in your content. To apply the inline code style, go to the source view and add the `outputclass` attribute in the desired content:

`outputclass="BoldItalic"`

The following example shows the Bold Italic format being applied at different places in the running text:

<img src="./assets/char-format-applied.png" width=500>

## Customize list style {#custom-list-style}

The List Styles contain the default style settings for the ordered and unordered lists. You can easily customize these list styles to meet your documentation requirements. 

In the following example, we will customize the numbered or ordered list style:

1. Open the required stylesheet for editing. 

   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand the **List Styles**. 

1. Select the **ol** style from the list. 

   The properties for the ol style are shown in the Properties panel along with its Preview.

   <img src="./assets/list-style-default.png" width=500>

1. Select the **Advanced Formatting** option. 

   A Confirmation message is displayed.  

1. Click **Yes** on the *Confirmation* message to open the **Advanced Formatting** properties. 

   The following properties are available by default:

   * **Level**: By default, there are 6 levels of numbered lists. The level that you select in this drop-down controls the style changes on the selected level and all subsequent levels. For example, if you select level 4, then all style changes that you apply are set on levels 4, 5, and 6.

   * **List Style Type**: There are a number of list numbering styles that you can choose from. The list contains locale-specific and generic numbering styles that are used to create a numbered list. Some of the list style types are Arabic, Cambodian, Devanagari, Ethiopic, Hangul, Hebrew, Japanese, Korean, Simple Chinese, Urdu, and more. 

   Further, you can work with the following Advanced Formatting properties:

   * **Number Format**: The default format is set to `<x>`, wherein the `x` value is replaced with the numbering Style that you selected in the List Style Type property. For example, if you have selected `decimal` (1) style, then the value of `x` auto-increments for every instance of the list element and goes as 2, 3, and so on. You can also add custom text in the field to format the list style. For example, if you want all first-level list styles to have a suffix "`)`", then you need to set this field for first-level list style as "`<x>)`".

   * **Insert Character**: If you want to add any special character in the Number Format, then click the Insert Character (<img src="./assets/insert-chars.png" width="25">) icon. Select the desired character that you want to add in the style format and click Insert. There are different types of special characters that you can choose from the Select Category drop-down list.

   * **Insert Level**: You can include the number from any of the preceding levels in your number format. For example, if you want to include the number format from 5th level in your 6th level number format, then choose 5 in the Insert Level drop-down list. Note that the Insert Level drop-down shows the numbers of only preceding levels and not the following level. For example, while you are at Level 3, the Insert Level list will only show levels 1 and 2. 

      <img src="./assets/list-insert-level.png" width="400">

      You can also change the Number Format to present the list values as required. For example, when you are using a nested numbering style for level 3, then you can format it as "`<2>.<x>))`". This will show list number 2, followed by a period, then followed by list number 3, and then two brackets, as `2.3))`.  

   * **Indent**: If you want to indent the list, then you need to set the Indent value. Any changes in the indent can be reviewed in the Preview panel and adjusted.

      >[!NOTE]
      >
      >You can enter the value in px (pixels), pt (points), rem, em, &#37; (percentage), or in (inches) units.

   * **Prefix Width**: This is the area that is occupied by the Number Format. It is automatically set to a size that can easily accommodate the selected format. If you want to increase the size, then you can replace the default value. 

      When setting this value manually, try changing the other properties that will have an impact on the width. For example, change the font size, the format with prefix or a suffix, and the various font properties to come up with the optimal size.  

   * **Spacing**: Specify the horizontal spacing in between the list number format and the content. The vertical spacing controls the gap between the two list items.  

      The following screenshot shows the customized ordered list for each level:
     
      <img src="./assets/list-number-format-final.png" width="500">

## Work with table style {#table-styles}

Using the stylesheets, you can design *n* number of table styles. Using the table styles, you can design how the entire table, a particular row or column. With control at cell-level styling, you can create very presentable table styles. 

In the following example, we see how to create a table style and the various table styling options that you can customize:

1. Open the required stylesheet for editing. 

   >[!NOTE]
   >
   >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, right-click on the **Table Style** and choose **New Style**. 

1. In the *Add Style* dialog, keep the **Tag** name as `table` and enter `double-border` in the **Class** name field.

1. Click **Done**. 

   A new table style named `table.double-border` is created and added under the Table Styles list. 

1. Select `table.double-border` from the **Table Styles** list, and set the following properties:

   * **Apply Formatting To**: You can choose to apply the style formatting to the entire table, odd&#47;even rows or columns, or first&#47;last row or column. 

      >[!NOTE]
      >
      >The following settings are available under the **General** section when **Apply Formatting To** is set to **Whole Table**.  

   * **Text Wrapping**: Select how to wrap text around the table. This is useful when the table is within another block-level element, and the table has to be rendered along with other content in the block element. The wrapping options are *left* or *right* aligned, or *none*. 

   * **Border Collapse**: Select the appearance of the table border. If you select collapse, then only a single border line is drawn in between the table cells. However, for separate style, the border is visible around each cell with additional padding.

      <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Border Spacing**: This setting is available only when Border Collapse is set to Separate. Using this setting, you can specify the vertical and horizontal spacing in between cell borders. 

      <img src="./assets/table-border-spacing.png" width="500">

      >[!NOTE]
      >
      >The following settings are available under the **Cell** section when **Apply Formatting To** is set to **Whole Table**.  

   * **Padding**: Specify the padding in between table cells. You can specify different padding values for top, bottom, left, and right sides. 

   * **Vertical Alignment**: Specify the vertical alignment for cell content. Available options are: Top, Middle, and Bottom.

   * **Border Side, Style, Color, Width, Radius:** Specify the border-related properties. You can choose to have borders only on specific sides like Left or Right. The Border Style lists the available border styles like Solid, Dashed, Double line, and more. Specify the border color using the color palette. You can specify the border width in px, pt, rem, em, &#37;, and in units. The Radius defines the curve to make circular corners. 

   The other properties under the Font, Border, Layout, Pagination, and Background are explained under other examples in this topic. Depending on your selection in the **Apply Formatting To** property, you can apply these values to the entire table or selected rows or columns.

   A preview of a sample table with different rows formatted in a different way is shown below:

   <img src="./assets/table-final-design.png" width="500">

## Work with other styles {#other-styles}

If you are working with structured (DITA) content, then you will notice that almost all DITA elements have a style mapping in the default stylesheet. For example, a `<shortdesc>` element's style is defined under **Other Style** > **.shortdesc** style definition. You can easily customize any of these styles and they get automatically applied in the PDF output generated from your structured content. This means that unlike other custom styles, you don't need to add an `outputclass` attribute on the content for these styles. 

In case you want to create a style definition for any element that is not available by default or you have a custom element, then you can easily create it in the stylesheet. The only point you must consider is to create the style with the same name as the structured element's name.

In the following example, we will create a new window's title (`wintitle`) style:

1. Open the required stylesheet for editing. 

      >[!NOTE]
      >
      >See [Customize a predefined or new style](components-pdf-template.md#customize-style) section for opening a stylesheet for customization or editing. 

1. In the **Styles** list, expand **Other Styles**. 

1. Right-click on the **Other Style** and choose **New Style**. 

1. In the *Add Style* dialog, keep the **Tag** name as *blank* and enter `wintitle` in the **Class** name field.

   As `wintitle` is a recognized DITA element name, its style definition is automatically mapped to the `<wintitle>` element in your source. 

1. Click **Done**. 

   A new style named `.wintitle` is created and added under the **Other Styles** list. 

1. Select .wintitle from the **Other Styles** list, and set the properties as required.

The following screenshot displays the wintitle style being applied to the text "Primary Control".

<img src="./assets/other-style-wintitle.png" width="500">
