---
title: Create maps based on customized templates
description: Learn how to Create maps based on customized templates
exl-id: 02513148-3876-4549-962a-9984f619030f
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


You can create map and topic templates in the following ways:
1. Templates pane of the [Left panel](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Templates in Assets UI](#templates-assets-ui)
1. [Options menu](#templates-in-assets-ui)

### Templates in Assets UI {#templates-assets-ui}

**Topic template**

Perform the following steps to create a topic template:

1.  In the **Assets UI**, navigate to the dita-templates folder.

    ![](images/dita-templates.png){width="800" align="left"}

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

    ![](images/create-dita-template.png){width="300" align="left"}

1.  On the Blueprint page, select **Map** and click **Next**.
1.  On the Properties page, specify the map template **Title**.
1.  Specify the file **Name**.

    >[!NOTE]
    >
    > The file name must have the .ditamap extension.

1.  (Optional\) Add a description.Click **Create**. The map template created message appears. You can then open the map template and edit it. You can add the references for the topic templates, map templates, and also other assets in the map template.

### Options menu {#options-menu}

To create a map or topic template, perform the following steps:
1. Select the **Map** or **Topic** folder in the `dita-templates` folder.
1. From the **Options** menu, select **Create Map Template** or **Create Topic Template**. 

    The **Create New Map Template** or the **Create New Topic Template** dialog opens.
1. Enter the title and the name of the new template. 
1. Choose the type of template that you want to create from the **Template** drop-down list.

The map template created message appears. You can add the template to your global or folder-level profile. The new template then appears in the topic or map creation process, and you can create maps or topics using it.


Your administrator can also create a folder and configure it to be the folder wherein you can create and save the templates. Learn how to [configure custom DITA template folder path](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) in the Installation and Configuration Guide. 


## Pass on the title defined in the templates

If you want to pass on the title of the topic or map used inside your template to the DITA maps created using that template, use curly brackets around the title.

Example
 
 ```XML
 <pubtitle>
    <mainpubtitle outputclass="booktitle">
    {title}
    </mainpubtitle>
    <subtitle>Subtitle</subtitle>
 </pubtitle>

 The resultant DITA map with title "Rootmap1" will look like as follows:
 <pubtitle>
    <mainpubtitle outputclass="booktitle">Rootmap1
    </mainpubtitle>
    <subtitle>Subtitle</subtitle>
 </pubtitle>
 ```

>[!NOTE]
> Only the first occurrence of curly bracket will be replaced with title.

If you do not use curly brackets around the title the resultant DITA map only the first element will be picked and the nesting of the title will not be picked from the template and it will look as follows:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> You can also use the curly brackets around the text to pass on its nested structure from the custom templates to your DITA maps.

Example

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




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

1. Click **Create**. The map created message appears.


The map generates all assets which are referred to inside the template folder. Some types of assets that are referred in a map can be as follows:

-   If the map contains the reference to a topic template, a copy of it is created inside the folder, in the same hierarchy as in the topics folder in the `dita-templates` folder.
-   If the map contains the reference to a map template, a copy of it is created inside the folder, in the same hierarchy as in the maps folder in the `dita-templates` folder.
-   If the map contains the generic reference to a topic or map outside the `dita-templates/topics` or `dita-templates/maps` folder, the same is only referred to, and no copy is created.

    >[!NOTE]
    >
    > `dita-templates/topics` and `dita-templates/maps` are the default paths in Guides and are configurable.


    If there is a topic template key definition inside the map template, a new key \(therefore new topic\) is created and referred to in the map.

-   If another map or topic is created at the same level in the folder, then the names of the newly created assets are appended with 0,1,2, and so on. You can choose to open the map for editing or save the map file in the repository.

**Parent topic:**[Work with the Map Editor](map-editor.md)
