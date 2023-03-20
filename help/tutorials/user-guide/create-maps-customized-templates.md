---
title: Create maps based on customized templates
description: Learn how to Create maps based on customized templates
---

# Create maps based on customized templates {#id225VF0808MP}

You can create customized map templates and use them to create DITA maps along with the topic templates and map templates referenced in the map template

You can refer to other map templates and topic templates from the customized map template. The referred map templates can refer to various map templates, topic templates, topics, maps, images, videos, and other assets. The customized map template can help you very easily replicate the map templates and the entire referred folder structure. These customized templates are especially useful to create and recreate multiple maps which have recursive structures and references.

    >[!NOTE]
    >
    > Topic templates are not created recursively. Only topic templates that are directly inside the map template are generated and any topic template inside a topic template is simply referred in the parent directly.

## Create customized templates 

AEM Guides allows you to create customized maps and topics from the dita-templates folder. You can use these customized templates to create your map and topic. You can also share these templates with your authors, and they can use them to create their files. Using these templates, you can allow the authors to keep separate copies of certain resources which are inside the templates folder.

    >[!NOTE]
    >
    > Any resources which are only to be referred to and maintained across must be kept outside the templates folder.

**Topic template**

Perform the following steps to create a topic template:

1.  In the **Assets UI**, navigate to the dita-templates folder.

    ![](images/dita-templates.png)

1.  Click **topics** folder to open it.Click **Create \> DITA Template**.
1.  On the Blueprint page, select **Topic** and then click **Next.**
1.  On the Properties page, specify the topic template **Title**.
1.  Specify the file **Name**

    >[!NOTE]
    >
    > The file name must have the .dita extension.

1.  \(Optional\) Add a description.
1.  Click **Create**. The topic template created message appears. You can then open the topic template and edit it.

**Map template**

Perform the following steps to create a map template:

1.  In the **Assets UI**, navigate to the dita-templates folder.
1.  Click **maps** folder to open it.
1.  Click **Create \> DITA Template.**

    ![](images/create-dita-template.png)

1.  On the Blueprint page, select **Map** and click **Next**.
1.  On the Properties page, specify the map template **Title**.
1.  Specify the file **Name**.
    >[!NOTE]
    >
    > The file name must have the .ditamap extension.

    \(Optional\) Add a description.Click **Create**. The map template created message appears. You can then open the map template and edit it. You can add the references for the topic templates, map templates, and also other assets in the map template.


## Use the map template to create new maps 

    >[!NOTE]
    >
    > The map template must be configured and made available for authoring by your administrator. For more details, see *Configure authoring templates* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

Perform the following steps to create a map using the custom map template:

1.  In the **Assets UI,** navigate to the folder where you want to create the map.
1.  Click **Create \> DITA Map**.
1.  On the Blueprint page, select the map template you want to use and click **Next**. For example, if you have created a map template 'test-template', select it.
1.  On the Properties page, specify the map **Title**.
1.  Specify the file **Name**.

    >[!NOTE]
    >
    > The file name must have the .ditamap extension.

    Click **Create**. The map created message appears.


The map generates all assets which are referred to inside the template folder. Some types of assets that are referred in a map can be as follows:

-   If the map contains the reference to a topic template, a copy of it is created inside the folder, in the same hierarchy as in the topics folder in the dita-templates folder.
-   If the map contains the reference to a map template, a copy of it is created inside the folder, in the same hierarchy as in the maps folder in the dita-templates folder.
-   If the map contains the generic reference to a topic or map outside the dita-templates/topics or dita-templates/maps folder, the same is only referred to, and no copy is created.

    >[!NOTE]
    >
    > dita-templates/topics and dita-templates/maps are the default paths in Guides and are configurable.

    If there is a topic template key definition inside the map template, a new key \(therefore new topic\) is created and referred to in the map.

-   If another map or topic is created at the same level in the folder, then the names of the newly created assets are appended with 0,1,2, and so on. You can choose to open the map for editing or save the map file in the repository.

**Parent topic:**[Work with the Map Editor](map-editor.md)

