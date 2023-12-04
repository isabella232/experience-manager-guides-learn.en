---
title: Include @navtitle attribute by default
description: Learn how to Include @navtitle attribute by default
---
# Include @navtitle attribute by default {#id2115BC0J0XA}

You can add different types of reference files in a map, for example topic, reference, task, \(sub\) maps, and so on. Most of these files support the `@navtitle` attribute. However, not many authors use it consistently. If you want to enforce usage of the `@navtitle` attribute in all referenced files in a map, then you can do so with a simple configuration.

Once enabled, every reference file that you add in a map will automatically get the `@navtitle` attribute added to its properties. The `@navtitle` will also get the value of the `title` element of the referenced content.

To include `@navtitle` attribute by default in reference files' properties, perform the following steps:

1.  Download the ui\_config.json file.

    You can make this change at the Global level or at a folder level profile. Depending on where you want to make this change, you need to download the respective ui\_config.json file. For more information about downloading ui\_config.json file, see [Configure and customize the XML Web Editor](conf-folder-level.md#id2065G300O5Z).

1.  Search for the `ditaAttributes` definition.

    The default definition of `ditaAttributes` is:

    ```json
    "ditaAttributes": {
    "attributes": [],
    "constraint": false,
    "required": {}
    },
    ```

1.  Change the `required` parameter as:

    ```json
    "required": {"navtitle": true}
    ```

1.  Save the file.

1.  Upload the file in the corresponding profile \(Global or Folder\).


With this configuration, every reference file that you add to a map will contain the `@navtitle` attribute by default.
