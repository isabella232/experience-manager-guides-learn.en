---
title: Set the Advanced Map Editor as default
description: Learn how to Set the Advanced Map Editor as default
exl-id: da5211af-74e1-4644-9c4e-70298a8bb677
---
# Set the Advanced Map Editor as default {#id181AI0003PN}

AEM Guides comes with a Basic Map Editor and an Advanced Map Editor. The Basic Map Editor gives you all necessary features to create your map file. The Advanced Map Editor is much more feature rich and it is integrated within the Web Editor. The Advanced Map Editor allows authors to create and edit DITA map files with an easy-to-use interface.

By default, whenever a new map file is created, it is opened in the Basic Map Editor. You can change this behavior by enabling the setting to open the Advanced Map Editor by default.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to enable the Basic Map Editor:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|``fmdita.hide.oldmapeditor``|Boolean \(true/false\). If you want to use the Advanced Map Editor by default, then set this property to true.<br> **Default value**: false |

>[!NOTE]
>
> By default, when an author creates a map file and chooses to open it for editing, then the Basic Map Editor is launched. When the Edit option is selected for a map file from the Assets UI, then also it is opened in the Basic Map Editor.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
