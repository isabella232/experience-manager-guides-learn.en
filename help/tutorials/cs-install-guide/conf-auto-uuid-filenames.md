# Configure auto-filenames based on UUID {#id205QG070D5Z}

By default, when a topic or map file is created, authors are given an option to specify the file name as well. Authors are free to assign the file names as per their requirements. However, this can bring in inconsistency and a wide range of files name can be seen in a large documentation system. As an administrator, you can restrict your authors from assigning file names for the files they create in your system. For every new topic or map file, you can choose to assign UUID-based file names automatically.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure auto-filenames based on UUID:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.uniquefilenames`|Boolean \(true/false\).\n **Default value**: false |

>[!NOTE]
>
> When this option is turned on, authors will not see the option to specify the file name while creating a new topic or map file. A new topic or map file can be created from the Assets UI and the Web Editor.

**Parent topic:**[Configure filenames](conf-file-names.md)

