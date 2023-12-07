---
title: Configure the option to edit in Oxygen
description: Learn how to configure the option to edit in Oxygen connector plugin.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
---
# Configure the option to edit in Oxygen

AEM Guides also allows the users to edit their DITA topics and DITA maps in the Oxygen connector plugin. 

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to configure the **Edit in Oxygen** option:



|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.editinoxygen`|Boolean \(true/false\). **Default value**: false |

>[!NOTE]
>
> This configuration is disabled by default and the option isn't available in the Web Editor.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
