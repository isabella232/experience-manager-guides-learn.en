---
title: Configure auto-filenames based on UUID
description: Learn how to Configure auto-filenames based on UUID
---
# Configure auto-filenames based on UUID {#id205QG070D5Z}

By default, when a topic or map file is created, authors are given an option to specify the file name as well. Authors are free to assign the file names as per their requirements. However, this can bring in inconsistency and a wide range of files name can be seen in a large documentation system. As an administrator, you can restrict your authors from assigning file names for the files they create in your system. For every new topic or map file, you can choose to assign UUID-based file names automatically.

Perform the following steps to automatically assign the UUID-based file name for all new files created in the system:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* bundle.

1.  Select the **Use UUID Based System Filenames** option.

1.  Click **Save**.


>[!NOTE]
>
> By default, this option is turned OFF. When this option is turned on, authors will not see the option to specify the file name while creating a new topic or map file. A new topic or map file can be created from the Assets UI and the Web Editor.

**Parent topic:**[Configure filenames](conf-file-names.md)
