# Configure display of UUID-based links {#id2035G20M0QN}

By default, when you create a link using the Insert Reference or Insert Reuse Content option in the Web Editor, the link is created using the UUID of the referenced content. The **Link** property \(in Properties panel\) of the referenced content can be configured to show the relative file path of the referenced content or the UUID. By default, the UUID of the referenced content is shown in the Properties panel.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to show the relative path or the UUID of the referenced content in the Web Editor:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.uuid`|Boolean \(true/false\). If you want to show the relative path of the linked content, then set this property to false. \n **Default value**: true |

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

