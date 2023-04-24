---
title:  Web Editor views
description: Learn how to  Web Editor views
---

# Web Editor views {#id204GK0D0V5Z}

AEM Guides' Web Editor supports viewing documents in three different modes or views:

## Author

This is a typical What You See is What You Get \(WYSISYG\) view of the Web Editor. You can edit topic as you would do in any regular rich-text editor. In the Author view, you have the options to save a revision of the document, find and replace content, insert element, insert hyperlink, insert content reference, and more.

>[!NOTE]
>
> When you use the content reference, the referred content is also displayed in Author view in blue color. The referred content is non-editable.

## Source

The Source view displays the underlying XML that makes up the topic. If you are comfortable working with XML directly, then you should use the Source view. In addition to making regular text edits in this view, you can also add elements and attributes using the Smart Catalog, or find and replace text, elements, or attributes.

-   To invoke the Smart Catalog, place the cursor at the end of any element tag where you want to insert the new element and enter "<". The editor shows a list of all valid XML elements that you can insert at that location. Use the arrow keys to select the element that you want to insert and press Enter. When you enter the closing bracket "\> the closing tag for the element is automatically added.

    ![](images/smart-catalog-elements.png){width="400" align="left"}

-   You can also change an element easily from the Source view. For example, if you change the opening tag of a `p` element to `note`, then the closing `p` tag is automatically changed to `/note`. In case you replace an element with an incorrect element, then you are immediately shown the Validation Error.

-   If you want to add an attribute to an element, place the cursor inside the element tag and press the Space bar. A list of valid attributes for that element is sown in the Smart Catalog. Use the arrow keys to select the desired element and hit Enter to insert the element. To specify a value for the attribute, enter the equals sign \(=\) and the editor automatically enters the opening and closing quotes "" wherein you can specify the attribute's value.

    ![](images/smart-catalog-attribute.png){width="350" align="left"}

-   In the Source view, there is an Auto Indent option that reorganizes the XML code in presentable and easily readable format. Also, if you select any text and switch from Author to Source or from Source to Author view, the selected text is also highlighted in the other view.
-   Another powerful feature in the Source view is the XML validation in your document. If you open a document containing invalid XML, it is opened in the Source view with the information about invalid XML. For example, in the following screenshot the exact information about the erroneous XML is given in the Parse Error pop-up.

    ![](images/invalid-topic-xml.png){width="650" align="left"}

    In the above screenshot, a cross highlight is used to point the line containing erroneous XML.

-   The Find and Replace feature allows you to search for any text, element, or attribute in the Source View. 
For more details, see the **Find and Replace** feature description in the [Main toolbar](web-editor-features.md#id#id2051EA0G05Z) section. 

-   The Source View provides many shortcuts to help you quickly navigate and work on a document. The following table lists the supported actions and their shortcut keys:

    |To do this|Use this shortcut|
    |----------|-----------------|
    |Add multiple cursors|**Ctrl**+Left click|
    |Multiple non-consecutive text selections|**Ctrl**+Left click to drag and select text|
    |Select text across and in between lines|**Alt**+Left click to drag and select text|
    |Undo multiple selection or exit full screen mode|**Esc**|
    |Show auto-complete|**Ctrl**+**Space**|
    |Go to the opening or closing tag of the current tag|**Ctrl**+**J**|
    |Expand or collapse the current tag and its content|**Ctrl**+**Q**|
    |Select the current element and its content|**Ctrl**+**L**|
    |Outdent the current element|**Shift**+**Tab**|
    |Delete the current element and its content|**Shift**+**Ctrl**+**K**|
    |Move cursor one word to the left|**Alt**+**Left Arrow**|
    |Move cursor one word to the right|**Alt**+**Right Arrow**|
    |Scroll one line up without changing the cursor location|**Ctrl**+**Up Arrow**|
    |Scroll one line down without changing the cursor location|**Ctrl**+**Down Arrow**|
    |Toggle full screen|**F11**|
    |Insert a new line after the current element|**Ctrl**+**Enter**|
    |Insert a new line before the current element|**Shift**+**Ctrl**+**Enter**|
    |Find and select the next occurrence of the current word|**Ctrl**+**D**|
    |Move the current element and its content one element up|**Shift**+**Ctrl**+**Up Arrow**|
    |Move the current element and its content one element down|**Shift**+**Ctrl**+**Down Arrow**|
    |Wrap the current element in comment tag|**Ctrl**+**/**|
    |Duplicate the current element and its content|**Shift**+**Ctrl**+**D**|
    |Delete text following the cursor. If cursor is before an opening element, then the entire element is deleted.|**Ctrl**+**K**+**K**|
    |Delete text to the left of the cursor in the current line. If the cursor is after the closing tag of an element, then the entire element is deleted.|**Ctrl**+**K**+**Backspace**|
    |Convert the current text to uppercase|**Ctrl**+**K**+**U**|
    |Convert the current text to lowercase|**Ctrl**+**K**+**L**|
    |Scroll the current element to the center of the editor|**Ctrl**+**K**+**C**|
    |Add a cursor above the current position|**Ctrl**+**Alt**+**Up Arrow**|
    |Add a cursor below the current position|**Ctrl**+**Alt**+**Down Arrow**|
    |Recursively find the current word \(in forward direction\)|**Ctrl**+**F3**|
    |Recursively find the current word \(in backward direction\)|**Shift**+**Ctrl**+**F3**|


## Preview

Opening a topic in the Preview mode shows how a topic will be displayed when it is viewed by a user in their browser. In case of a DITA map, a preview of the map is shown wherein a single composite document of all topics within the map is shown.

The Preview mode gives you the following functionalities:

-   [View content based on conditional filters](#id2114BI00VXA)
-   [View the track changes markups](#id2114BJ00CE8)
-   [Export a topic as PDF](#id2114BL00B5U)

### View content based on conditional filters {#id2114BI00VXA}

If you have used conditions in your topic or map, those conditions are shown in the Filters panel. By default, all conditions are selected and the entire content is displayed. If you deselect a condition, then the content having that condition is removed from the view. You can also choose to highlight conditionalized content.

The following image shows a topic that uses two conditions — `Audience` and `Product`. The conditionalized content is highlighted with yellow background.

![](images/preview-filters.png){width="800" align="left"}

### View the track changes markups {#id2114BJ00CE8}

If a document contains track changes markups \(or visual cues\), then you can also preview the document with or without those markups. While previewing a document, the right panel contains the Filters and Tracking options.

![](images/preview-tracking_cs.png){width="400" align="left"}

There are three **Tracking** options that you can choose from:

-   **No Markup**: In this view, all insertions and deletions are accepted, and a simple view of the document is presented. In this view, you do not see any track changes markups.
-   **Original**: In this view, all insertions are rejected and all deletions are restored back, and then a preview is shown. Simply, you get the original form of the document before you enabled the track changes mode.
-   **Show Markup**: In this view, you get all markups for inserted and deleted content.

    The following image shows the preview of a map file with markups:

    ![](images/preview-map-with-track-changes.PNG){width="800" align="left"}


### Export a topic as PDF {#id2114BL00B5U}

PDF is one of the most common output formats that is used at every possible stage of the document development cycle. AEM Guides provides you the flexibility to generate the PDF of an individual topic or an entire map file. Export as PDF feature allows the Author, Publisher, or an Administrator to easily generate the PDF output for an individual topic. It uses the DITA-OT configurations saved at the folder-level profile to generate the PDF.

This feature supports the following functionalities:

-   Generate the PDF of the currently active working copy of a topic.
-   Accept the DITA-OT transformation name and command-line arguments to generate the PDF.
-   Save the generated output on local system.
-   Resolve key and content references used in the topic before generating the output.

To export a topic as PDF, follow these steps:

1.  Open the topic in Preview mode.

1.  Click the **Export as PDF** \(![](images/export-as-pdf-icon.svg)\) icon.

    The Export as PDF dialog is displayed.

    ![](images/export-as-pdf-dialog.png){width="350" align="left"}

1.  *\(Optional\)* Specify the DITA-OT transformation name and any command-line arguments that you want to use.

1.  Click **Download**.

    >[!NOTE]
    >
    > Ensure that you have enabled the pop-up window in the browser configuration, else the PDF will not get downloaded.

    The PDF is generated and opened in a new tab or you are shown a dialog to save the PDF on your local system.


**Parent topic:**[Work with the Web Editor](web-editor.md)

