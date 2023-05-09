# Migrate non-DITA content {#id181AH0R02HT}

This section guides you through the migration process to migrate non-DITA documents into DITA format. AEM Guides provides migration from the following sources:

-   [Microsoft Word](#id1949B040Z5Z)

-   [InDesign documents](#id195AD0B0K5Z)

-   [XHTML](#id1949B04L0Y4)

-   [Unstructured FrameMaker documents](#id1949B050VUI)

-   [Any other structured document](#id1949B0590YK)


## Migrate Microsoft Word documents {#id1949B040Z5Z}

AEM Guides allows you to migrate your existing Word documents \(`.docx`\) into DITA topic type documents. You need to specify the input and output folder locations along with other parameters and the document gets converted into DITA document. Depending on the content, you could have a .dita file and a .ditamap file.

To be able to convert a Word document successfully, your document should be well structured. For example, your document should have a Title, followed by Heading 1, Heading 2, and so on. Each of the headings should have some content in it. If your document is not well structured, the process might not work as expected.

By default, AEM Guides uses the [Word-to-DITA \(Word2DITA\) transformation framework](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). This transformation depends on the [style-to-tag mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) configuration file. To be able to use the Word2DITA transformation successfully, you must consider the following guidelines for preparing your Word document for conversion:

>[!NOTE]
>
> If you make any changes in the default style-to-tag mapping configuration file, then you must update and use the guidelines confirming to your updated style mapping.

-   Ensure that your document starts with a Title; this Title is mapped to the DITA map title. Also, the Title must be followed by some regular content.

-   After the Title, there should be Heading 1, Heading 2, and so on. Each Heading must have some content in it. The Headings are converted into new Concept type topics. The hierarchy of the generated topics is as per the Heading levels in the document, for example, Heading 1 will precede Heading 2, and Heading 2 will precede Heading 3 content.

-   The document must have at least one Heading type content.

-   Ensure that you do not have any grouped images. In case you have grouped images in your document, ungroup all such images.

-   Remove all headers and footers.

-   Inline styles such as bold, italics, and underline are converted into `b`, `i`, and `u` elements.

-   All ordered and unordered lists are converted into `ol` and `ul` elements. This also applies to nested lists, lists within tables, notes, or footnotes.

-   All hyperlinks are converted into `xref`.

-   The filename of the converted files is based on the heading text followed by a file number. The file number is a sequential number based on the position of the heading text in the document. For example, if a heading text is "Sample Heading" and it is 10th heading in the document, then the resultant filename for this topic will be similar to Sample\_Heading\_10.dita.


Perform the following steps to convert your existing Word documents into DITA topic type document:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/config/w2d_io.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/w2d_io.xml`

    The `w2d_io.xml` file contains the following configurable parameters:

    -   In the `inputDir` element, specify the location of the input folder wherein your source Word documents are available. For example, if your Word documents are stored in a folder named `wordtodita` in `projects` folder, then specify the location as: `/content/dam/projects/wordtodita/`

    -   In the`outputDir` element, specify the location of the output folder or keep the default output location to save the converted DITA document. If the specified output folder does not exist on DAM, then the conversion workflow creates the output folder.

    -   For the `createRev` element, specify whether a new version of the converted DITA topic is to be created \(`true`\) or not \(`false`\).

    -   In the `s2tMap` element, specify the location of the map file that contains mappings for Word document styles to DITA elements. The default mapping is stored in the file located at:

        ```XML
        /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
        ```

        >[!NOTE]
        >
        > For more information about the structure of `word-builtin-styles-style2tagmap.xml` file and how you can customize it, see [Style to Tag Mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) in *DITA For Publishers User Guide*.

    -   In the props2Propagate element, specify the properties that should be passed on to the DITA map. This property is required to pass on the default metadata like dc:title,dc:subject,dam:keywords,dam:category from document metadata to converted DITA assets.

1.  Save the `w2d_io.xml` file.

1.  After configuring the required parameters in the `w2d_io.xml` file, log into AEM and open the Assets UI.

1.  Navigate to the input folder location \(`wordtodita`\).

1.  Upload the source Word documents into this folder. For information on uploading content on DAM, see [Upload existing DITA content](migrate-content-upload-existing-dita-content.md#).


Using the `config` `/config` block, you can define one or multiple blocks of configurations for conversion. The conversion workflow gets executed and the final output in the form of a DITA topic is saved in the location specified in the `outputDir` element.

## Migrate Adobe InDesign documents {#id195AD0B0K5Z}

AEM Guides allows you to convert InDesign documents. Similar to FrameMaker, InDesign also allows you to create unstructured and structured documents. The unstructured documents use the paragraph and character styles to format content. The structured document use elements and their corresponding attributes.

The conversion process requires mapping the paragraph and character style formats to relevant DITA elements. Similarly, in case of structured documents, the mapping file will contain one-to-one mapping of InDesign elements and attributes with DITA elements and attributes.

The conversion process involves the following actions in the backend:

-   The *InDesign Markup Language* \(IDML\) file is unpacked to a working directory.
-   The designmap.xml file is read to locate the individual InDesign stories.
-   All stories are merged into a single XML instance, 'empty' stories are discarded.
-   All embedded graphics are exported.
-   Pre-conversion of standard structures such as tables and graphics into DITA format.
-   Style or structure mapping to final output based on the mapping file.
-   Creation and validation of individual DITA topics and DITA map files.
-   Deletion of temporary files.

Broadly, the conversion process requires you to[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) [Prepare InDesign files for conversion](appendix.md#id195DBF0045Z)[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) and [Prepare the mapping file for InDesign to DITA migration](appendix.md#id194AF0003HT)[appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT), [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT)then you need to follow the given procedure of running the conversion process.

Perform the following steps to convert your existing InDesign documents into DITA topic type document:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/config/idml2dita_io.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/idml2dita_io.xml`

    Configure the following parameters in the `idml2dita_io.xml` file:

    -   In the `inputDir` element, specify the location of the input folder wherein your source InDesign documents are available. For example, if your InDesign documents are stored in a folder named `indesigntodita` in `projects` folder, then specify the location as: `/content/dam/idmlfiles/indesigntodita/`

    -   In the`outputDir` element, specify the location of the output folder or keep the default output location to save the converted DITA document. If the specified output folder does not exist on DAM, then the conversion workflow creates the output folder.

    -   In the `mapStyle` element, specify the location of the map file that contains mappings for InDesign document styles to DITA elements. The default mapping is stored in the file located at:

        ```XML
        /stmap.adobeidml.xml
        ```

        >[!NOTE]
        >
        > For more information about the structure of `stmap.adobeidml.xml` file and how you can customize it, see the [Prepare the mapping file for InDesign to DITA migration](appendix.md#id194AF0003HT) section [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) in Appendix.

1.  Save the `idml2dita_io.xml` file.

1.  After configuring the required parameters in the `idml2dita_io.xml` file, log into AEM and open the Assets UI.

1.  Navigate to the input folder location \(`indesigntodita`\).

1.  Upload the source InDesign documents into this folder. For information on uploading content on DAM, see [Upload existing DITA content](migrate-content-upload-existing-dita-content.md#).


## Migrate XHTML documents {#id1949B04L0Y4}

AEM Guides allows you to convert your existing XHTML documents into DITA topic type documents. You need to specify the input and output folder locations along with other parameters and the documents get converted into DITA format. There are two methods that you can use to convert your structured HTML documents:

-   Upload all documents into the input folder, or
-   Create a ZIP of all documents along with the media files and upload it into the input folder. This approach is generally used for a set of HTML files that are linked to each other and there is a table of contents \(index.html\). The index.html file contains links to all HTML files in the set.

Whether you upload all files individually or bundled in a ZIP, the conversion process creates a one-to-one mapping between the HTML files and the resultant DITA files. This essentially means that there is a .dita file created for each .html file in the input folder.

The following points must be considered for uploading your documents in a ZIP file:

-   All referenced topics should be placed within the ZIP file.

-   All referenced media files should be referred within the topic files using relative link.

-   Create an index.html file and add links to the topics that you want to add in the TOC. This index.html file is used to create the DITA map file. In the index.html file, you can also create nested topics listing as shown in the following code sample:

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <html
    xmlns="http://www.w3.org/1999/xhtml">
        <head>
            <title>Sample Index File</title>
        </head>
        <body>
            <h1>Sample Index</h1>
            <div class="content">
                <ul class="book">
                    <li class="topicref">
                        <a href="Topic1.html">Topic 1</a>
                        <ul class="book">
                            <li class="topicref">
                                <a href="Topic1-1.html">Topic 1.1</a>
                            </li>
                            <li class="topicref">
                                <a href="Topic1-2.html">Topic 1.2</a>
                            </li>
                        </ul>
                    </li>
                    <li class="topicref">
                        <a href="Topic2.html">Topic 2</a>
                    </li>
                </ul>
            </div>
        </body>
    </html>
    ```

    Note that every `ul` tag must have the `class` attribute set to `book`. Similarly, every `li` tag's `class` must be set to `topicref`.

-   If you use inline styles, then convert the inline styles to CSS-based style classes in your XHTML file. Then use style-attribute mapping to convert these classes-based styles to DITA `outputclass` attribute in the converted DITA file.

    While generating HTML or AEM Site output from these DITA files, the `outputclass` attributes can be used to apply style-class on generated HTML or AEM Site to match your source HTML content.


Apart from the considerations for creating the ZIP file, your XHTML document must also be well structured. For example, your document should have a *Title*, followed by *Heading 1*, *Heading 2*, and so on. Each of the headings should have some content in it. If your document is not well structured, the migration process might not work as expected.

To convert your existing XHTML document into DITA topic, perform the following steps:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/config/h2d_io.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/h2d_io.xml`

    The `h2d_io.xml` file contains the following configurable parameters:

    -   In the `inputDir` element, specify the location of your input folder wherein your source XHTML documents are available. For example, if your XHTML documents are stored in a folder named `xhtmltodita` in `projects` folder, then specify the location as: `/content/dam/projects/xhtmltodita/`

    -   In the`outputDir` element, specify the location of your output folder or keep the default output location. If the specified output folder does not exist on DAM, then the conversion workflow creates the output folder.

    -   For the `createRev` element, specify whether a new version of the converted DITA topic is to be created \(`true`\) or not \(`false`\).

1.  Save the `h2d_io.xml` file.

1.  After configuring the required parameters in the `h2d_io.xml` file, log into AEM and open the Assets UI.

1.  *\(Optional\)* You can also add the related links section to the converted documents. Perform the following steps to enable this feature:

    >[!NOTE]
    >
    > By default, the related links section is not created in the converted documents.

    1.  Navigate to the h2d.xsl file in the following location:

        /libs/fmdita/html2dita/

    2.  Search for the following parameter:

        `<xsl:param name="generate-related-links" select="false()"/>`

    3.  Set the value of the above parameter to `true()`.
    4.  Save and close the file.
1.  Navigate to the input folder location \(`xhtmltodita`\).

1.  Upload the source XHTML documents into this folder. For information on uploading content on DAM, see [Upload existing DITA content](migrate-content-upload-existing-dita-content.md#).


Using the `<config> </config>` block, you can define one or multiple blocks of configurations for conversion. The conversion workflow gets executed and the final output in the form of a DITA topic is saved in the location specified in the `outputDir` element.

## Migrate unstructured FrameMaker documents {#id1949B050VUI}

AEM Guides allows you to convert your existing unstructured FrameMaker \(`.fm` and `.book`\) documents into DITA documents. The first step is to create style mappings using FrameMaker and save those settings in a .sts file. Next, if you are using custom DITA, then you can map your custom elements with the source FrameMaker formats in the `ditaElems.xml` file. For example, if you have created a custom element named `impnote` to handle all important notes, then you can define this custom element in the `ditaElems.xml` file. Once this custom element is defined, AEM Guides would not raise an error while converting FrameMaker document containing `impnote` element.

Also, If you want to specify some additional attributes with your custom or valid DITA element, you can define those in the style2attrMap.xml file. For example, you can specify the `type` attribute with the value of `important` to be passed on with the `impnote` element. This additional information can be specified in the style2attrMap.xml file.

In addition to specifying

To convert your existing unstructured FrameMaker documents into DITA format, perform the following steps:

1.  Create style mappings in FrameMaker and save those settings in a .sts file.

1.  Log into AEM and open the CRXDE Lite mode.

1.  If you have custom DITA elements, define those in the `ditaElems.xml` file available at the following location:

    `/libs/fmdita/config/ditaElems.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/ditaElems.xml`

    The `ditaElems.xml` file contains a single configurable parameter:

    -   In the `elem` parameter, specify the name of the custom element that you want to use in your converted DITA documents. This element would be passed on as is in the generated DITA documents.

1.  If you want to specify additional attributes, define those in the `style2attrMap.xml` file available at the following location:

    `/libs/fmdita/config/style2attrMap.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/style2attrMap.xml`

    The `style2attrMap.xml` file contains the following configurable parameters:

    -   In the `fmStyle` parameter, specify the source format used in the FrameMaker document that you want to map.

    -   In the`ditaAttr` element, specify the DITA attribute that you want to map with the source format.

    -   In the `ditaVal` element, specify the value for the mapped attribute. If you don't have any value, you can leave this entry blank.

1.  Save the `style2attrMap.xml` file.

1. After configuring the required parameters in the `style2attrMap.xml` file, log into AEM and open the Assets UI.

1. Navigate to and click on the FrameMaker document that you want to convert.

    The DITA map console appears showing the list of Output Presets available to generate output.

1. Select DITA output format and configure the required parameters.

    >[!NOTE]
    >
    > You must use the same settings file \(.sts\) that you created in FrameMaker. Also, specify the Settings Name and Destination Path.

1. Click the **Generate** icon to start the output generation process.


Using the `<attrMap> </attrMap>` block, you can define one or multiple blocks of configurations for conversion. Depending on the content, you could have a .dita file and a .ditamap file as the converted files.

## Migrate any other structured document {#id1949B0590YK}

AEM Guides allows you to convert your existing structured documents into valid DITA documents. You need to specify the input and output folder locations, the location of your transformation file, the extension with which the final output is saved, and whether a new version of the document is required or not.

To convert your existing structured documents into DITA format, perform the following steps:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/config/XSLConfig.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/XSLConfig.xml`

    The `XSLConfig.xml` file contains the following configurable parameters:

    -   In the `inputDir` element, specify the location of your input folder wherein your source structured documents are available. For example, if your structured documents are stored in a folder named `xsltodita` in `projects` folder, then specify the location as: `/content/dam/projects/xsltodita/`

    -   In the`outputDir` element, specify the location of your output folder or keep the default output location. If the specified output folder does not exist on DAM, then the conversion workflow creates the output folder.

    -   In the `xslFolder` element, specify the location of the folder where the XSL transformation files are stored.

    -   In the ``xslPath`` element, specify the location of the primary .XSL file that is used to initiate the conversion process.

    -   In the ``outputExt`` element, specify the file extensions of the final output file that is created from the transformation stream.

    -   For the `createRev` element, specify whether a new version of the converted DITA topic is to be created \(`true`\) or not \(`false`\).

1.  Save the `XSLConfig.xml` file.

1.  After configuring the required parameters in the `XSLConfig.xml` file, log into AEM and open the Assets UI.

1.  Navigate to the input folder location \(`xsltodita`\).

1.  Upload the source structured documents into this folder. For information on uploading content on DAM, see [Upload existing DITA content](migrate-content-upload-existing-dita-content.md#).


Using the `<config> </config>` block, you can define one or multiple blocks of configurations for conversion. The conversion workflow gets executed and the final output in the form of a DITA topic is saved in the location specified in the `outputDir` element.

**Parent topic:**[Migrate existing content](migrate-content.md)

