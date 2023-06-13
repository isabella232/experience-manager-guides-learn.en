# Configure Regx for valid file name characters {#id214BD0550E8}

Starting with AEM Guides 3.8 release, as an administrator, you can define a list of valid special characters allowed in file names. In earlier releases, users were allowed to define file names containing special characters such as `@`, `$`, `>`, and more. These special characters resulted in issues while opening topics from DITA map dashboard or clicking on topic's link in the TOC, which often resulted in the page not opening because of special characters in the URL.

Using the configuration that allows you to define a regx for valid file name characters, you have full control on how the files are named internally in the system. You can define a list of special characters that are allowed in the file names. By default, the valid file name configuration contains "`a-z A-Z 0-9 - _`". While creating a new file, you can have any special character in the file's title, but internally it will get replaced with "`-`" in the file name. For example, you can have the file's title as "Introduction 1" or "Introduction@1", the corresponding filename generated for both these cases would be "Introduction-1".

When you define a list of valid characters, remember that these characters "`*/:[\]|#%{}?&<>"/+`" will always be replaced with a "`-`".

If you do not configure the valid special characters list, the file creation process might give you some unexpected results. To avoid such errors, it is strongly recommended to make this configuration change.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure regex for valid file name characters:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`valid.characters`|The value is a regex pattern. It must have three basic characters and the list must start with a hyphen \(-\).

**Default value**: \[-a-zA-Z0-9\_\]

|

>[!NOTE]
>
> Similar to the list of valid file name characters, you can also specify a list of valid file name character for AEM Site output. For more details, see [Configure valid file names for AEM Site output](conf-file-names-valid-regx-aem-site-output.md#).

**Parent topic:**[Configure filenames](conf-file-names.md)

