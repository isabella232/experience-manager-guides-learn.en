---
title: Configure prompt to save as a new version on close
description: Learn how to Configure prompt to save as a new version on close
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
---
# Configure prompt to save as a new version on close {#id222HBI00XXA}

When the user tries to close a file that is opened in the Web Editor using the **Close** button on the file's tab or the **Close** option in the Options menu, a dialog appears if the file has unsaved data or an unsaved version. The user is prompted to save the file as a new version if the version is not saved.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure a prompt to save as a new version on close:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.savenewversion`|Boolean \( true/ false\). <br>  **Default value**: true |

When this configuration is enabled, the **Save as a New Version** checkbox is selected by default in the dialog box.

For more details, see *File close and save scenarios* section in the Using Adobe Experience Manager Guides as a Cloud Service guide.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
