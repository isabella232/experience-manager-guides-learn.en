---
title: Configure display of UUID-based links
description: Learn how to Configure display of UUID-based links
exl-id: 734e913f-4132-4c76-bee5-d3ef8ba91ae3
---
# Configure display of UUID-based links {#id2035G20M0QN}

By default, when you create a link using the Insert Reference or Insert Reuse Content option in the Web Editor, the link is created using the UUID of the referenced content. The **Link** property \(in Properties panel\) of the referenced content can be configured to show the relative file path of the referenced content or the UUID. This display is controlled by the **Enable UUIDs** option in the configMgr. By default, it is turned ON, which implies that the UUID of the referenced content is shown in the Properties panel.

Perform the following steps to show the relative path or the UUID of the referenced content in the Web Editor:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, the **Enable UUIDs** option is enabled by default. This implies that UUID of the referenced content is shown in the **Link** property in the Properties panel.

    If you want to show the relative path of the linked content, then deselect the **Enable UUIDs** option.

1.  Click **Save**.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
