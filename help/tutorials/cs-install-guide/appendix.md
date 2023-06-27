---
title: Appendix
description: Learn how to prepare InDesign documents for migration
---

# Appendix {#id195AD0L60Y4}

## Troubleshooting AEM Guides 

Once you have installed and configured AEM Guides, you can troubleshoot the issues.

## Validate references 

You can run the given scripts to validate the references. These scripts can help you identify the broken references and then patch or fix them.

-   `/bin/fmdita/validatebtree?operation=validate` - reports any broken content references but doesn't fix them.

-   `/bin/fmdita/validatebtree?operation=patch` - lists the broken content references and patches or fixes them.


**Validate script**

Perform the following steps to check the references, using the validate script available in the product package:

1.  Run the validate script \[`/bin/fmdita/validatebtree?operation=validate`\] to check if for any new broken references.
1.  In case the validate script reports any errors, you can patch it using the patch script.
1.  Record the below-given details and if necessary, share them with your customer success team:
1.  -   Logs printed by validate script
-   Package of "`/content/fmdita/references`"
-   Any other required details depending on the scenario reported

**Patch script**

Perform the following steps to patch any broken references, using the patch script available in the product package:

1.  Run the patch script `[/bin/fmdita/validatebtree?operation=patch]` to fix the broken references. The script execution takes a few minutes and prints the logs as it progresses. Once the execution completes, it prints "`Done`" at the end.

   >[!NOTE]
   >
   > It is recommended that you copy and save the logs for reference purpose.

1.  Once the patch script is executed successfully, you can perform the following checks:
1.  -   Check a new node "`references_backup_<timestamp>"` has been created under `/content/fmdita`
-   Check that the references have been fixed

**Logger**

You can also create a separate logger for this script execution, as per the details given below:

-   Add a logger on class "`adobe.fmdita.common.BTreeReferenceValidator`"
-   Set it to `DEBUG`

The created log file will record all the information that is related to script execution and is useful in case the browser session timeouts, while triggering the script from the browser.

## Prepare InDesign files for conversion {#id195DBF0045Z}

InDesign provide authors with a rich set of features for creating attractive and complex documents. Often this means that the various parts of a document are placed on the page visually, but with no attempt to provide any flow between those text frames. When the '*reading order*' of the text frames is not defined, the IDML file will contain stories that may not follow any meaningful order. The end result will be one or more DITA topics with paragraphs, tables and graphics in a random order.

While it is possible to edit the DITA content into a sensible order in a DITA editor, it is much easier to fix the InDesign file before creating the IDML file. This can be done without altering the look of the source document. It also has the benefit of making the source document accessible by properly defining the reading order.

***Threading text frames***

InDesign uses the term *'threading'* for the process of linking one frame to another. For more details about threading text frames, see *[Threading text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* topic in InDesign documentation.

***Overlapping frames***

Some InDesign documents use un-threaded overlapping frames for layout reasons. It may be very difficult to merge this content into the main thread. The best option may be to edit the result in the DITA environment.

***InDesign stories***

Each threaded flow of content in an InDesign document is a called a '*story*'. For best results, it is recommended to keep the number of stories limited. However, there are some parts of your document that may not be needed in the DITA output. For example, page footers are rarely need, but may appear in the middle of a topic if they are not handled carefully.

The easiest way to exclude text that is not required in the document is to give it a special *Paragraph Tag* that is only used for the unwanted content. For example, instead of reusing a *\[Basic Paragraph\]* for the footer, create a dedicated *Footer* tag. Then in the MapStyle file simply set the *Footer* paragraphs to be dropped like this:

```
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mapping to DITA doctypes***

It is essential that your source document has at least one Paragraph style or Element that can mark the start of a topic. It is common for documents to use *Heading1* as the name of the top-level titles in the document. You can then create a mapping from that style to a specific DITA doctype. If your document is well organized and the use of *Heading1* is constant throughout, then you will get good results.

***Multiple DITA doctypes***

If some of the *Heading1* paragraphs are need to convert to different DITA doctypes, then duplicate the paragraph style in InDesign. Give these styles an easy to recognize name such as *Heading1\_genTask* or *Heading1\_troubleshooting* as appropriate. Then, setup the mapStyle file as shown below:

```
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Structured InDesign documents***

InDesign has a loose relationship with XML. While a document can include an XML DTD and the main story may be valid against that DTD, it is also possible to create hybrid documents where some of the content is XML, but no DTD is included. These are the undesirable cases for a successful conversion to DITA. If a document contains XML parts, try to save the output to XML and see if the results are acceptable. If not, then DITA content will also include invalid content, or may fail completely.

***Table formatting***

The conversion from InDesign table formatting rules to the equivalent table formatting in DITA is a complex process. This is due to the rich formatting features available in the source files compared to the basic options provided by the Oasis \(CALS\) table model used in DITA. Vertical and horizontal text alignment is provided and gives similar results although Justified text is always justified according to the text direction, while InDesign allows Left Justified and Right Justified.

InDesign's handling of column and row separators is again far more capable than the Oasis table model's basic options. InDesign provides four cell borders—Border type \(solid or pattern\), Border weight, Border color, Border tint, Border gap color and border gap tint. All of these have to be mapped down to borders on the right and bottom of each cell \(entry element\) where the only choices are 0 or 1 – hide the border or show the border.

Border ruling in InDesign can be applied at the following levels:

-   Table Styles
-   Cell Styles
-   Local overrides on each cell

The InDesign to DITA conversion process applies the border ruling as follows:

-   Table Styles are mapped to the `colspec/@colsep` attribute for vertical rules. Horizontal rules are mapped to the `row/@rowsep` attribute. In both cases, if the border is not defined, then the attribute is not created.
-   Cell Styles are mapped to the `entry/@colsep` and `entry/@rowsep` attributes. These values will override any Table Style derived border ruling.
-   Local overrides apply the formatting directly to the cell and override Table Styles and Cell Styles.

***Alternating patterns***

InDesign Table Styles allow column and cell ruling to follow an alternating pattern. While this feature is supported for conversion, the results will only be obvious when one pattern group maps to show ruling \(1\) and the other pattern group maps to hide ruling \(0\).

## Prepare the mapping file for InDesign to DITA migration {#id194AF0003HT}

The correct DITA conversion requires a mapping file that matches the contents of the source document. For unstructured InDesign documents, this means all available Paragraph Styles and Character Styles need to be mapped. For XML structured InDesign documents all elements in its associated DTD must be mapped.

The mapping files for unstructured and structured InDesign documents are different. This is due to the more complex processing requirements for converting unstructured source content to DITA.

A sample of the mapping file is given below:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

The mapping file is an XML file with a simple structure that lists all the source paragraph styles and character style codes. The file contents are explained below:

**Style Mapping**

In the `styleMap` element, you can specify two optional attributes – `@map_date` and `@map_version` for recording the version of the mapping file.

**Document Type**

The `doctypes` element lists the supported DITA map and topic mappings.

**Map document type paragraph rules**

The `mapDoctypeParaRule` element is mandatory. This element's attributes must not be edited because the source XML's root element is always mapped to the DITA map's root `map` element.

**Document type paragraph rule**

The `doctypeParaRule` element is mandatory. This gives the conversion process a way to identify the start of a new topic. Normally the `@style` attribute is used on its own with the `@local` attribute set to 0. However, if there are always local formatting overrides on the chosen style, you will have to add a rule for each style plus its local overrides. This is simple to recognize in the generated mapping file where it would be possible to find this or similar:

```
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

In the above example, there are two `paraRule` elements for `@style` = "Heading1". Simply, create an equivalent `doctypeParaRule` elements with the `@mapToDoctype` attribute set as required.

The attributes used in the `doctypeParaRule` are explained below:

-   `@style`: The name of a style in the source InDesign document.
-   `@local`: See [\#id194CG0V005Z](#id194CG0V005Z).
-   `@mapToDoctype`: The name of a DITA topic type from an enumerated list of all valid `doctypes`.

**Element wrapping rules**

The element wrapping rules define the ways to wrap or move elements in the incoming document into a predefined element according to a set of attribute values.

***`wrap` element***

This is an optional element. The `wrap` element lists the elements that will be wrapped or moved. Wrapping is typically used where a series of elements must be given a common parent element. For example, multiple `li` elements being wrapped in a `ol` element. Additionally, `wrap` can be used for moving elements such as titles for figures and tables.

The attributes used in the `wrap` are explained below:

-   `@element`: A plus sign after an element name shows that all adjacent elements with the same name will be wrapped in the element named in the `@wrapper`attribute.
-   `@wrapper`: The name of the wrapping element.
-   `@context`: Provides a way to further refine how a given element is wrapped. The following example shows a way to map a series of `li` elements in either an ordered list `ol` or an unordered list `ul` according to the `@context` value \(the context is defined on the `paraRule` element\):

    ```
    <wrap elements="li+" context="number" wrapper="ol">
       <attributeRules createID="true"/>
    </wrap>
    <wrap elements="li+" context="bullet" wrapper="ul">
       <attributeRules createID="true"/>
    </wrap>
    ```


The following example shows how to create a `fig` element from a `title` and an `image` element:

-   `@elements`: The elements listed and separated by a comma will be wrapped in the element named in the `@wrapper` attribute. Due to the common practice of including figure titles below the image, the title will be the `title` element immediately following the `image`.

    The following wrap rule:

    ```
    <wrap elements="title, image" context="FigTitle" wrapper="fig">
       <attributeRules createID="true"/>
    </wrap>
    ```

    Converts the following intermediate XML:

    ```
    <image href="Links/myImage.png" scale="59">
       <title>IDML2DITA workflow</title>
    ```

    Into the following valid DITA figure structure:

    ```
    <fig id="id397504">
       <title>IDML2DITA workflow</title>
       <image href="Links/myImage.png" scale="59">
    </fig>
    ```

-   `@wrapper`: The name of the wrapping element.
-   `@context`: Provides a way to further refine how a given element is wrapped \(the context is defined on the `paraRule` element\).

The following example shows how to move a `title` into a `table`:

-   `@elements`: The `title` element that is located either immediately before or immediately after a `table` will be wrapped in the element named in the `@wrapper` attribute. An XPath-style predicate can identify the position of the title element as `[before]` or `[after]`.

    Example: The following wrap rule:

    ```
    <wrap elements="title[before]" context="TableTitle" wrapper="table">
       <attributeRules createID="true"/>
    </wrap>
    ```

    Converts the following intermediate XML:

    ```
    <title>IDML2DITA workflow</title>
    <table id="id289742" outputclass="BasicTable">
       <tgroup cols="2">
          <colspec colname="0" colwidth="0.7*">
             <colspec colname="1" colwidth="0.3*">
    ```

    Into this valid DITA figure structure:

    ```
    <table id="id289742" outputclass="BasicTable">
       <title>IDML2DITA workflow</title>
       <tgroup cols="2">
          <colspec colname="0" colwidth="0.7*">
             <colspec colname="1" colwidth="0.3*">
    ```

-   `@wrapper`: The name of the wrapping element.

-   `@context`: Provides a way to further refine how a given element is wrapped \(the context is defined on the `paraRule` element\).


**Paragraph style rules**

The `paragraphStyleRule` elements are described below:

** `paraRule` element**

The `paraRule` element is mandatory. This specifies the mapping rules for all Paragraph Styles. In an InDesign document, all text is contained within sub-structure of Paragraph Styles, even paragraphs without any style are named `\[No paragraph style\]`. The square brackets, these indicate a built-in InDesign style name.

>[!NOTE]
>
> The square brackets indicate a built-in InDesign style name.

The attributes used in the `paraRule` are explained below:

-   `@style`: The name of a style in the source InDesign document.
-   `@local`: See [\#id194CG0V005Z](#id194CG0V005Z).
-   `@mapTo`: The name of a DITA target element.

-   `@context`: This attribute is used to link to a specific **wrap** rule when more than one wrapper choice is available. Example: the `li` element may be wrapped in either an `ol`, or a `ul` element. To identify the different list types, you may use a specific style name or the `@local` attribute which can show the following:
    -   `local="p[-|-|-|-|-|b|-|-]"` Where the '`b`' in field 6 indicates a bulleted list item. In this case set `@context` to '`bullet`'.
    -   `local="p[-|-|-|-|-|n|-|-]"` Where the '`n`' in field 6 indicates a numbered list item. In this case set `@context` to '`number`'.

-   `@commentOut`: This attribute enables the wrapping of the target element in XML comments so that the information is not lost but can be handled manually by the user. This is useful if the source content cannot be forced to conform to DITA structure rules.

-   `@refactor`: This optional attribute has a choice of two values:

-   `unwrap`: The matched element is removed while retaining its content.

-   `drop`: The matched element and all its content is removed.


**Character style rules**

The `charRule` elements are described below:

>[!NOTE]
>
> There will be no mapping for the built-in character style `[No character style]` when `local="0"`, because they are removed during the preprocessing.

***`charRule` element***

This is an optional element.

These are the mapping rules for all Character Styles. In an InDesign document, all text is contained within child elements of Character Styles.

The attributes used in the `charRule` are explained below:

-   `@style`: The name of a style in the source InDesign document.
-   `@local`: See [\#id194CG0V005Z](#id194CG0V005Z).
-   `@mapTo`: The name of a DITA target element.
-   `@refactor`: This optional attribute has a choice of two values:
    -   `unwrap`: The matched element is removed while retaining its content.

    -   `drop`: The matched element and all its content is removed.


**Attribute rules**

This element can be a child of the following element contexts:

-   `mapDoctypeParaRule`
-   `mapDoctypeElemRule`
-   `doctypeParaRule`
-   `doctypeElemRule`
-   `paraRule`
-   `charRule`
-   `elementRule`

The purpose of attribute rules is to manage the attributes for the matched elements.

Depending on the context, the following attributes are available the `attributeRules` element:

-   `@createID`: Generates a unique ID for the matching elements. Allowed values `true` or `false`. Available in all contexts.
-   `@copyAll`: Copies all attributes from the source XML content for structured source files only. Allowed values are `true` or `false`. Available for contexts `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` and `elementRule`.


The attributes used in the `attributeRules` are explained below:

>[!NOTE]
>
> This element can contain multiple child elements.

-   `addNew`: Adds a new attribute to the matched element. Available for all contexts. It has two attributes:
    -   `@name`: Must be a legal XML name, preferably valid for the DITA context.
    -   `@value`: Can be literal text or a simple XPath expression.
-   `copyAtt`: Copies a single attribute to the target while optionally renaming it in the process. The value is not changed. Available for contexts `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` and `elementRule`. When this element is present the `@copyAllAtts` value is assumed to be `false`. It has two attributes:
    -   `@name`: Must be the name of an attribute present on the source XML element.
    -   `@mapTo`: Must be a legal XML name, preferably valid for the DITA context.

**Local formatting codes**

In any InDesign document, it is possible for paragraph styles and character styles to carry several hundred different formatting overrides. Most of these properties provide no useful role in the conversion process. However, we have identified a core set of formatting features that do affect the semantics of the document and need to influence the conversion process.

The `@local` attributes are presented as a special delimited format where eight fields are provided along with a prefix to show the type of formatting override. The formatting codes fields are listed below:

-   Prefix **p** for para style local override or **c** for character style local override.
-   **Font style** which is the family name and properties such as '***Bold Condensed Italic***'.
-   **Font size** in points.
-   **Character position** for superscript or subscript.
-   **Under** for underscore.
-   **Strike** for strikethrough.
-   **List code** to identify list type as bulleted or Numbered – not always used by InDesign.
-   **Bullet code** lists all defined bullet types in the document.
-   **Number code** lists all defined numbering styles in the document.

Careful use of this feature allows otherwise lost local formatting can help to improve the quality of a transfer from styled content into DITA. This example can be resolved to mean Italic, 16pt text in a bulleted list: `p[Italic|16|-|-|-|b|-|-]`.

**Structure Mapping**

The structure mapping file is similar to the Style Mapping file with a simple structure that lists all the source element and relevant attribute types. Two attributes, `@map_date` and `@map_version` are provided for recording the version of the mapping file to be used.

**Document Type**

The `doctypes` element lists the supported DITA map and topic mappings.

**Map document type element rules**

The `mapDoctypeElemRule` element is mandatory. This element's attributes must not be edited because the source XML's root element is always mapped to the DITA map's root `map` element.

**Element wrapping rules**

See [\#id194CG600NY4](#id194CG600NY4).

**`elementRules` element**

This lists all [\#id194CGC00SHS](#id194CGC00SHS)elements.

**`elementRule` element**

The `elementRule` element is mandatory. These are the mapping rules for all source elements. While an InDesign document does contain unstructured style elements, these are ignored for structured content unless the '***hybrid mode***' processing is enabled.

The attributes used in the `elementRule` are explained below:

-   `@elementName`: The name of an element in the source InDesign document.

-   `@local`: See [\#id194CG0V005Z](#id194CG0V005Z). \(Only useful for Hybrid documents\).

-   `@mapTo`: The name of a DITA target element.

-   `@refactor`: This optional attribute has a choice of two values:

    -   `unwrap`: The matched element is removed while retaining its content.

    -   `drop`: The matched element and all its content is removed.

-   `@context`: This attribute is used to link to a specific wrap rule when more than one wrapper choice is available. Example: the `li` element may be wrapped in either an `ol`, or a `ul` element.

-   `@commentOut`: This attribute enables the wrapping of the target element in XML comments so that the information is not lost but can be handled manually by the user. This is useful if the source content cannot be forced to conform to DITA structure rules.


