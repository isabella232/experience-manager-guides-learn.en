---
title: Upload existing DITA content
description: Learn how to Upload existing DITA content
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
---
# Upload existing DITA content {#id176FF000JUI}

Most likely you would have a repository of existing DITA content that you would like to use with the AEM Guides. For such existing content, you can use any of the supported methods explained in [Add digital assets to Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html).

## Configure UUID filename pattern 

When you import content, it is not necessary that your file names will be based on the UUID. In a system that uses UUID-based file names, it is mandatory that all files are referred using their UUIDs rather than their original file names. If an imported file doesn't have UUID-based file names, you can configure the system to add a UUID to their file property. This UUID is then used to refer such files where UUID is not used for naming the files.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure UUID filename pattern:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`|`uuid.regex`|String specifying the regex for UUID filename pattern. <br> If a file doesn't follow the specified pattern, a UUID is added to the file's property and all references to the file are updated with the UUID assigned to the file. <br> **Default value**: `"^GUID-(?<id>.*)"` |

## Use curl commands 

You can also use curl commands to create a folder in DAM, upload files, and add metadata on the uploaded content.

**Create a folder**

Run the following command to create a folder in AEM repository:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specify the following parameters to create a folder:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have the folder creation privileges.

-   `jcr:primaryType=sling:Folder`: Specify this parameter *as is* to create a folder type resource.

-   `<server folder path>`: Complete folder path including the name of the new folder that you want to create in the AEM repository. For example, if you specify the path as `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, then the folder `AEM-Guides` is created within the `projects` folder in DAM.


**Upload a file**

Run the following command to upload a file in the AEM repository:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specify the following parameters to upload a file:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have write privileges on the `server folder path`.

-   ``local file path``: Complete file path on your local system that you want to upload.

-   `<server folder path>`: Complete folder path on the AEM server where you want to upload the file.


**Add metadata**

Run the following command to add metadata on a file:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specify the following parameters to add metadata information:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have write privileges on the ``metadata node path``.

-   ``-F<attribute name>=<value>``: The `<attribute name>` is the name of the metadata attribute, such as `audience` and the `<value>` could be `internal`. You can specify multiple attribute name-value pairs separated by space.

-   `<metadata node path>`: Complete folder path including the file name and its metadata node. For example, if you specify the path as `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, then the specified metadata information is set on `intro.xml` file.


**Parent topic:**[Migrate existing content](migrate-content.md)
