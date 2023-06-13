# Configure prompt to check in a file on close {#id222HC040PE8}

When the user tries to close a file that is opened in the Web Editor using the **Close** button on the file's tab or the **Close**option in the Options menu, a dialog appears if the file has unsaved data or an unsaved version. The user is prompted to unlock the file if it is locked.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure a prompt to check in a file on close:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.checkin`|Boolean \( true/ false\).

 **Default value**: false

|

When this configuration is enabled, the **Unlock the File** checkbox is selected by default in the dialog box.

For more details, see *File close and save scenarios* section in the Using Adobe Experience Manager Guides as a Cloud Service guide.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

