---
title: Configure file auto-save in the Web Editor
description: Learn how to Configure file auto-save in the Web Editor
---

# Configure file auto-save in the Web Editor {#id199CC0J0M5Z}

One of the most common features in the browser-based editor it the ability to save data after a specific period of time. The AEM Guides Web Editor also supports auto-saving of topic and map files at the specified time interval. When this feature is triggered, the working copy of the topic or map is saved. A new version of the topic or map is not created. To create a new version, you have to click the Save Revision icon in the Web Editor's toolbar.

The auto-save feature is not enabled by default and you need to enable this using the configuration file.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure file auto-save and auto-save time interval:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.autosave`|Boolean \(true/false\).<br> **Default value**: false |
|`xmleditor.autosaveinterval`|Specify the time interval in seconds to trigger the auto-save feature.|

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

