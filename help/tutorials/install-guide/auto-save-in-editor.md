---
title: Configure file auto-save in the Web Editor
description: Learn how to Configure file auto-save in the Web Editor
---
# Configure file auto-save in the Web Editor {#id199CC0J0M5Z}

One of the most common features in the browser-based editor it the ability to save data after a specific period of time. The AEM Guides' Web Editor also supports auto-saving of topic and map files at the specified time interval. When this feature is triggered, the working copy of the topic or map is saved. A new version of the topic or map is not created. To create a new version, you have to click the Save Revision icon in the Web Editor's toolbar.

The auto-save feature is not enabled by default and you need to enable this from the configMgr. Perform the following steps to enable the auto-save feature in the Web Editor:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, select the **Auto Save** option.

1.  In the **Auto Save Interval** field, specify the time interval in seconds to trigger the auto-save feature.

1.  Click **Save**.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
