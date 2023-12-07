---
title: Auto-generate element IDs
description: Learn how to Auto-generate element IDs
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
---
# Auto-generate element IDs {#id20CIL40016I}

AEM Guides generates a document ID for any new document that you create. For example, when you create a DITA map, an ID like `map.ditamap_random_digits` is assigned to the map's ID. You can also define elements on which an ID is automatically generated and assigned.

AEM Guides provides easy configuration settings wherein you need to define the elements on which an ID is auto-generated and a pattern for the ID. By default, some elements like `section`, `table`, `ul`, `ol`, are configured for auto-generation of ID. You can add other elements to this list so that whenever these elements are inserted in a document, AEM Guides generates and assigns an ID based on the given pattern

Perform the following steps to configure elements to have auto-generated ID:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, specify one or more elements in the **Auto Generate IDs for Element Tags** field.

    >[!NOTE]
    >
    > Element tags are the DITA element names such as `body`, `title`, `codeblock`, and so on. To specify multiple elements, separate element names with a comma.

1.  In the**Pattern for Generating IDs** field, specify a pattern to generate an ID.

    The default value for this field is set to `${elementName}_${id}`. The `${elementName}` value is replaced with the name of the element. The `${id}` variable generates sequential number for the element. For example, if you assign the paragraph element to have auto-generated IDs, then the first paragraph in the topic or document will get an ID like p\_1, the next paragraph will get p\_2, and so on. However, in a different document, the ID generation process restarts. This means that in a different document, IDs like p\_1 and p\_2 can be assigned to paragraph elements.

    If your document already contains IDs in the specified pattern, then the auto-generation process does not assign those IDs to new elements.

1.  Click **Save**.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
