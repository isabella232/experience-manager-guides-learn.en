---
title: Configure custom DITA topic template
description: Learn how to Configure custom DITA topic template
exl-id: f79165ef-5118-4574-815d-c4ecb2f7d58b
---
# Configure custom DITA topic template {#id16A7G0O02TD}

The AEM Guides comes with the following DITA topic templates:

-   Topic

-   Task

-   Concept

-   Reference

-   Glossary

-   Troubleshooting

-   Blank


You can use any of these templates to create topics templates as per your authoring requirements. The Blank DITA template does not contain any structure or elements like the other templates. You can use the Blank template as the base, if your template is highly customized and is not based on any regular DITA topic templates.

To customize DITA topic template and use it for authoring, you need to perform the following three main tasks:

1.  *\(Optional\)* [Configure custom DITA template folder path](#id191LCF0095Z)

1.  [Create custom authoring template](conf-folder-level.md#id1917D0EG0HJ)

1.  Add a custom template into the global or folder-level profile as explained in the [Configure authoring templates](conf-folder-level.md#id1889D0IL0Y4) section


## Configure custom DITA template folder path {#id191LCF0095Z}

AEM Guides allows you to configure a folder to store your customized DITA map and templates. By default, the template files are stored in the following folder in DAM:

`/content/dam/dita-templates/`

To manage topic and map template files, there are dedicated folders to store the topic and map templates. By default, all topic templates are stored under the `/content/dam/dita-templates/topics`

folder. All map templates are stored under the `/content/dam/dita-templates/maps` folder.

As an administrator, you can choose to create custom map or topic templates in the default folder or create your own folder to store custom templates. If you plan to use the default folder, then you can skip this process.

To configure a folder for your custom DITA topic templates, perform the following steps:

>[!IMPORTANT]
>
> You can skip this process if you want to use the default folder to store custom templates.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  In the **Templates Location** property, specify a location to store custom templates.

1.  Click **Save**.


If the specified location exists in DAM, then all default map and topic templates are copied into that folder. If the location does not exist, then the folder is created with all default map and topic templates.

**Parent topic:**[Configure topic and map templates](conf-template-tags.md)
