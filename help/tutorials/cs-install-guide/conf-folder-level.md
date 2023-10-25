---
title: Configure global or folder-level profiles
description: Learn how to Configure global or folder-level profiles
exl-id: ba8fb637-d36a-4f25-bfdd-bc713a30effd
---
# Configure global or folder-level profiles {#id181AH2003PF}

In an enterprise, different groups or products may use different authoring templates, output templates, conditional attribute profiles \(or subject schemes\), and Web Editor configurations. Configuring these only at an enterprise \(or global\) level can make authors experience difficult, as they will see templates or profiles that are not relevant to them.

AEM Guides allows you to configure authoring \(topic or map\) templates, output templates, conditional attribute, and Web Editor configurations at an enterprise \(global\) level as well as at a folder level. This way, you can segregate the configurations for different departments or products in your enterprise.

Also, you can delegate the folder-specific configurations to a department or product administrators to decentralize the administration.

Using the Folder Profiles tile in the Guides settings, you can configure settings under the following tabs:

![](assets/folder-profile-tabs.png){width="800" align="left"}

-   **General**: The general tab is only available when you are configuring folder-level \(or project/product\) settings. You can configure settings such as the folder paths on which the settings will be applicable and users who will have administrative rights to create or update configurations.

-   **Conditional Attributes**: Use this tab to configure conditional attributes at global or folder-level. A conditional attribute is a combination of the attribute name and value, and you can also define a label for it. You can use the standard DITA attributes or your own custom attributes. The conditional attributes that you define at the global level are made available to all users across projects. In case you have defined folder-level conditional attributes, then they are merged with the globally defined conditional attributes.

-   **Authoring Template**: Use this tab to configure the templates that your authors will use to create DITA content. The following topic templates are available out-of-the-box:

    -   Glossary

    -   Reference

    -   Topic

    -   Concept

    -   Task

    -   Troubleshooting

    -   Blank

    -   DITAVAL

    >[!NOTE]
    >
    > You can use any of the existing templates as a base to create new templates. The Blank DITA template does not contain any structure or elements like the other templates. You can use any of the OOTB DITA templates as the base, make modifications to it, and save it with a different name. After making the required changes, add the updated template to the global or folder-level authoring templates configuration, then it becomes available for authoring.

    Along with topic templates, you can also define the map templates that will be made available to authors. The following map templates are available out-of-the-box:

    -   Map

    -   Bookmap

-   **Output Preset**: Similar to Authoring Templates, there are five pre-configured output presets:

    -   AEM Site

    -   PDF

    -   HTML5

    -   EPUB

    -   Custom

    Publishers can use these out-of-the-box output presets to publish content. These presets can be configured by an administrator of the global or folder-level profile. Once configured, the publishing presets become available to the publishers for newly created DITA maps. You can also apply publishing presets to existing DITA maps, see [Apply preset changes](#id18AGD0K0OHS) for more details.

-   **XML Editor Configurations**: Use this tab to customize the look-and-feel and various features of the Web Editor. The following configurable settings are available for the Web Editor:

    -   XML Editor UI Configuration
    -   CSS Template Layout
    -   XML Editor Snippets
    -   XML Content Version Labels
    -   Rootmap \(only at folder level\)

You can configure both — global profile and folder-level profile. In a folder-level profile, you can define the folders on which the settings will be applicable. These settings include the conditional attributes, authoring templates, output presets, and XML Editor settings. The conditional presets, authoring templates, and XML Editor configurations are then made available to authors who work in the configured folders. Similarly, publishers will have access to the configured output presets defined within the configured folders.

A folder-level profile overrides the settings configured in the global profile. In other words, if a folder has a folder-level profile, then it will show the authoring templates, output templates, and XML Editor settings configured in its corresponding folder profile. It will not show the settings configured in the global profile. However, this does not apply to the conditional attributes. In case of conditional attributes, the conditional attributes are merged at global and folder levels.

The following sections walk you through the process of configuring global profile and folder-level profiles.

## Configure global profile 

Perform the following steps to configure the global profile:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click the **Folder Profiles**.

    For the first time the Folder Profiles page is shown with only the Global Profile tile.

    ![](assets/folder-profile-global.png){width="800" align="left"}

1.  Click on the **Global Profile** tile.

1.  To configure **Conditional Attributes**, see [Configure conditional attributes for global or folder-level profiles](#id1889D0I305Z).

1.  To configure **Authoring Template**, see [Configure authoring templates](#id1889D0IL0Y4).

1.  To configure **Output Presets**, see [Configure output presets](#id18AGD0IH0Y4).

1.  To configure XML Editor Configuration, see [Configure and customize the XML Web Editor](#id2065G300O5Z).

1.  After making all required updates, save and close the **Global Profile**.


## Create and configure a folder-level profile 

Perform the following steps to configure a folder-level profile:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click on the **Folder Profiles** tile.

    For the first time, the Folder Profiles page is shown with the default Global Profile tile only.

1.  Click **Create**.

    ![](assets/create-folder-profile.png){width="300" align="left"}

1.  Enter the following details in the **Create Folder Profile** dialog:
    -   Name of the folder profile.
    -   Path of the folder where the profile will be applicable.

        >[!NOTE]
        >
        > You cannot apply multiple folder profiles on a folder. Ensure that the folder you are selecting here does not have any other profile applied to it. In case of a parent-child folders having their own specific profiles, the child folder will use the configurations from its own profile. The configurations from the parent folder do not override the configurations of a child folder.

1.  Click **Create**.

    A new tile with the name of the folder profile is created in the Folder Profiles page

1.  Click on the folder profile tile to edit.

    A General tab with the folder profile's name and configured folder information is shown.

1.  Click **Edit** to add multiple folders and users who will have administrative access to modify the folder profile.

    >[!NOTE]
    >
    > Users that you add here will have the administrative rights to update the conditional attributes, authoring template, and output presets configured for this folder profile.

1.  To add a folder, click the Browse icon in the Folder Path and navigate to and select a folder, and click Add to add the folder to this profile.

    >[!NOTE]
    >
    > Ensure that the folder that you choose here does not have any other folder-level profile associated with it.

1. To add a user, select a user from the **Admin Users** drop-down and click **Add**.

    >[!NOTE]
    >
    > You can add multiple users to the folder profile from the drop-down list. You can also remove an existing admin user from the list by clicking the delete icon next to the user ID.

1. After adding all required folders and users to the folder profile, click **Save**.


Now you are ready to configure the conditional attributes, authoring templates, output presets, and XML Editor.

>[!IMPORTANT]
>
> When you create a folder profile, by default it does not contain any authoring templates. You must add the required authoring templates in the folder profile to make them available to your authors.

## Configure conditional attributes for global or folder-level profiles {#id1889D0I305Z}

Perform the following steps to configure standard DITA-supported conditional attributes at global or folder-level:

1.  Log into Adobe Experience Manager as an administrator or the user having administrative rights on a folder-level profile.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click on the **Folder Profiles** tile.

1.  Click on the profile tile that you want to configure.

    >[!NOTE]
    >
    > You can choose to configure conditional attributes in the Global Profile or a folder-level profile.

1.  On the profile page, click on the **Conditional Attributes** tab.

1.  Click **Edit**.

1.  Click **Add**.

1.  Enter the **Name**, **Value**, and a **Label** for the conditional attribute.

    You can save a profile with only the attribute name. However, an attribute can only be used when it has a value specified to it. If you specify both - value and label for an attribute, the Web Editor shows the label of the conditional attribute. Also, the label is shown to the publishing administrator at the time of creating a conditional preset.

    The following screenshot shows the definition for the `platform` attribute with possible values and labels.

    ![](assets/add_profile.png)

1.  If you want to add more values for the same attribute, click the **+** icon and enter the additional value and label.

1. If you want to add more attributes, click **Add**.

1. Click **Save**.


If you are using custom attribute, then it must be a valid DITA attribute supported by the DTD. If you want to use any attribute, which is not a standard DITA attribute, then perform the following additional steps:

1.  Add the custom attribute to the DTD file. For example, if your DTD file is commonElements.mod, then you need to locate this file in the DTD directory. The default path of the system DTD file is:

    /libs/fmdita/dita\_resources/DITA-1.3/dtd/base/dtd/commonElements.mod

    >[!IMPORTANT]
    >
    > The specialized DTD file should be a part of the custom code deployment. DTDs under /apps are part of the product deployment and hence it is overwritten with installation of any new release. It is recommended to add specialized DTD under /var/dxml/dita\_resources within the project folder, and include the DTD/catalog path in the DITA profile.For more information, see [Integrate DITA specialization](dita-ot-specialization.md#id211MB0E00XA).

1.  Use the Package Manager to download /libs/fmdita/config/condAttrList.xml file:

1.  Create a copy of the condAttrList.xml file at the following location in your Cloud Manager's Git repository:

    `/apps/fmdfmdita/config/condAttrList.xml`

1.  Save the file.

1.  Add custom attributes to the global or folder-level profile.


## Configure authoring templates {#id1889D0IL0Y4}

AEM Guides comes with 7 out-of-the-box authoring templates and 2 DITA map templates. You can choose to have only a few templates available to your authors. In case you use a custom template, the same can be configured and made available for authoring. You use the Authoring Template tab in the Folder Profiles configuration to add or remove topic, map, or PDF templates from global or folder-level profiles.

Even before configuring the topic, map, or PDF templates at global or folder-level, you can also define a location to store your custom authoring templates. To configure a custom location to store authoring templates, see [Configure custom DITA template folder path](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z).

Perform the following steps to add the topic, map, or PDF templates into a folder profile:

1.  Log into Adobe Experience Manager as an administrator or the user having administrative rights on a folder-level profile.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click on the **Folder Profiles** tile.

1.  Click on the profile tile that you want to configure.

    >[!NOTE]
    >
    > You can choose to configure authoring template in the Global Profile or a folder-level profile.

1.  On the profile page, click on the **Authoring Template** tab.
1.  Click **Edit**.

    You get the options to add Topic, Map, and PDF templates by searching from the default location or browsing for it.

    >[!NOTE]
    >
    > By default, all authoring templates are stored in the /content/dam/dita-templates folder. The `dita-templates` folder contains `topics`, `maps`, and `PDF` sub-folders to store the topic, map, and PDF templates. You can add your custom templates \(.dita,.xml, or .ditamapfiles\) in the default template folders. Once you add your template in the default folder, you will be able to add them in the global or folder profile. For more information about creating custom templates using the Web Editor, see [Create custom authoring template](#id1917D0EG0HJ).

    ![](assets/search-author-temp.png){width="800" align="left"}

1.  Add the required topic, map, and PDF templates to your profile.

    To add a template, do one of the following:

    -   Choose **Search or Type** and enter or select the name of a template from the drop-down list. The drop-down list consists of all default templates and any new template that you have created.

        ![](assets/default-template-list.png){width="300" align="left"}

    -   Click **Browse** and select a template from DAM.

1.  Click **Add**.

    The selected templates are added to the template list.

    ![](assets/author-templ-added-list.png){width="800" align="left"}

    >[!NOTE]
    >
    > You can change the order of templates by dragging and dropping them at the desired position in the list. The position of templates controls the order in which they show in the Blueprint page in the topic or map creation workflow.

1.  To set the translation rules, browse the SRX location to find the folder which contains the SRX files. The SRX \(Segmentation Rules eXchange\) format is a standard for exchanging segmentation rules between different users and different translation environments. You can create a folder and add your custom SRX files to it.

    Once you've created the folder which contains the SRX files, you can add the folder path in the **Translation SRX location**configuration inside your folder profile.

    AEM Guides picks the SRX rules according to the source language of the translation project. It looks for a custom SRX file for a language, and if you do not define a custom SRX file, then it picks the rules as per the out of the box translation rules.

1. Click **Save**.


In case you have configured the templates on a folder-level profile, the configured templates get associated with the configured folder. All projects created under the configured folder will have access to only those templates that are configured under the folder-level profile.

## Create custom authoring template {#id1917D0EG0HJ}

AEM Guides provides an easy way of creating authoring templates. As a system administrator, you can use the Web Editor to create authoring templates from scratch. You can then add the new template in the global profile or assign it to a specific folder using the folder-specific profile.

Perform the following steps to create a custom authoring template:

1.  Log into Adobe Experience Manager as an administrator.

1.  In the Assets UI, navigate to the folder configured to store the template files. By default, all topic templates are stored in the /content/dam/dita-templates/topics folder.

    >[!NOTE]
    >
    > To configure a custom location to store topic or map templates, see [Configure custom DITA template folder path](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1.  Click **Create** \> **DITA Template**.

1.  On the Blueprint page, select the type of the DITA topic template that you want to create.

    >[!NOTE]
    >
    > You can use the Blank template to start from scratch. The Blank template does not have any structure or elements in it.

1.  Click **Next**.

1.  On the new template Properties page, enter a **Title**, **Name**, and **Description** for the template.

    >[!NOTE]
    >
    > The name is automatically suggested based on the Title of your template. If you want to manually specify the name, then ensure that the Name does not contain any spaces, apostrophe, or braces and ends with .dita.

1.  *\(Optional\)* Click the **Add a Thumbnail** button to browser for and select a thumbnail to associate with your template.

1.  Click **Create**.

    The Topic Created message appears.

    You can choose to open the template for editing in the Web Editor, or save the template file in the template store location. Once the template is created, you can use the Web Editor to customize the template as per your authoring needs. Once a template is in place, ensure that you associate it either with a global or folder-level profile.


## Configure output presets {#id18AGD0IH0Y4}

In a typical enterprise setup, different output templates could be used for different products or user guides. Also, there could be some common output generation processes that should be used by all publishers and a set of specific output generation processes for a specific group of publishers or projects.

AEM Guides allows the administrator to create output presets with specific settings that can then be used by all or a specific set of publishers to generate output. For example, the administrator can create one output preset to generate a user guide that is common across all publishers. And, another one to create the programming user manuals that are specific to a set of publishers. Both of these presets can be configured to use different output templates. In this example, the common publishing preset for generating the user guide can be configured at the global level. And, the output preset for generating the programming user manual can be configured at a folder-level.

Once the default output presets have been created in the system, all DITA maps created after that will use the default presets to generate output. However, all existing DITA maps would continue to use the output presets that were earlier configured with them. If you want to apply the new output preset on all existing DITA maps, then you need to run the Apply preset changes workflow.

In addition to the presets configured at the global or enterprise level, a publisher would still have the rights to create more output presets. However, those presets are tied to the DITA map for which they are created. For more details about creating regular output presets for a DITA map, see *Create, edit, duplicate, or remove an output preset* in the Using Adobe Experience Manager Guides as a Cloud Service guide.

Perform the following steps to configure global or folder-specific output presets:

1.  Log into Adobe Experience Manager as an administrator or the user having administrative rights on a folder-specific profile.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click on the **Folder Profiles** tile.

1.  Click on the profile tile that you want to configure.

    >[!NOTE]
    >
    > You can choose to configure output presets in the Global Profile or a folder-specific profile.

1.  On the profile page. click on the **Output Presets** tab.

    A list of out-of-the-box output presets is displayed, which includes AEM Site, PDF, HTML5, EPUB, and CUSTOM.

1.  Do one of the following to create or edit an output preset:

    -   Click **Create** to create a new output preset from scratch.
    -   Click Duplicate to create a copy of the selected output preset. You can make changes to the duplicate preset and save it.

    -   Click **Edit** to open the selected preset's configuration for editing.

        For information about output preset settings, see *Understanding the output presets* in the Using Adobe Experience Manager Guides as a Cloud Service guide.

1.  Click **Save** to save the preset settings.


All DITA maps created or uploaded after this will have the new or updated output preset.

## Apply preset changes {#id18AGD0K0OHS}

A new output preset created at the global level is made available to all new DITA maps that you create going forward. Similarly, if a new output preset is created at a folder-level, then that preset is made available to all maps that will be created in the configured folder. By default, a new output preset is not made available to any existing DITA map.

If you have updated an existing output preset, or you want to make a new output preset available to existing DITA maps, then perform the following steps:

1.  Log into Adobe Experience Manager as an administrator or the user having administrative rights on a folder-specific profile.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click on the **Folder Profiles** tile.

1.  Click on the profile tile that you want to configure.

    >[!NOTE]
    >
    > You can choose to configure output presets in the Global Profile or a folder-specific profile.

1.  On the profile page. click on the **Output Presets** tab.

    A list of out-of-the-box output presets is displayed, which includes AEM Site, PDF, HTML5, EPUB, and CUSTOM.

1.  Select the output preset that you want to apply to existing DITA maps.

1.  Click **Apply Preset Changes** in the main toolbar.

1.  In the Apply Preset Changes dialog, you can choose from:

    -   **Selecting Overwrite Existing Preset option**: If you select this option, then any updates that you made in the existing output presets will overwrite settings in all existing DITA maps where that preset is used. However, doing so will result in the loss of any existing conditional preset and baseline information associated with the map.

    -   **Not selecting Overwrite Existing Preset option**: If you do not select this option, then any updates that you made in the existing output presets will not impact the existing DITA maps. Only the newly added presets are added to the existing DITA maps. Note that the newly created DITA map gets both—the updated output presets and the newly added presets.

1.  Click **OK** to apply changes from the selected output presets on all existing DITA maps.


## Configure and customize the XML Web Editor {#id2065G300O5Z}

By default, the XML Web Editor comes with a lot of features to help your authors create DITA documents. If you work in a restrictive environment, you can choose which features are exposed to your authors. The XML Editor Configuration tab allows you to easily control the features and also change the look-and-feel of your Web Editor. As an administrator, you can customize the following components of the Web Editor:

**XML Editor UI Configuration**

This setting controls the toolbar and the other user interface elements of the Web Editor. Click the Download icon to download the ui\_config.json file on your local system. You can then make changes to the file and the upload the same. Depending upon where you are uploading the file at, global or folder-level profile, the changes are applied accordingly. For more details about how to customize the XML Editor using the ui\_config.json file, see [Customize toolbar](conf-web-editor-customize-toolbar.md#).

**CSS Template Layout**

Download the file available in this section to customize the look-and-feel of your document when it is previewed or opened for editing in the Web Editor. The default CSS file available for download is only a test file, which should not be used for customization. You can create a CSS file with customizations for the Web Editor and upload the same. For example, you can create a .css file with the following code:

```
.title {    font-size: 9em;}
```

Save this file and upload it in the CSS Template Layout section. The next time you download the file, you will get the latest CSS file being used in the Web Editor.

**XML Editor Snippets**

Using the configuration file in this section, you can create some default snippets and share them with your authors. The default structure of the file is given below:

```
{
   "snippetID": {
      "name": "snippet Name",
      "description": "snippet Description",
      "value": "<i>this is snippet value</i>"
  }
}
```

The following details are required to create a snippet:

snippetID
:   A unique ID for the snippet. It can take an alphanumeric value.

name
:   A descriptive name to identify the snippet. This name shows up in the Snippets panel.

description
:   Add a descriptive information for the snippet.

value
:   Provide the XML code of the snippet.

>[!NOTE]
>
> You can add more snippets by adding a comma \(,\) at the end of your snippet definition and repeating the same structure for the next snippet.

**XML Content Version Labels**

By default, authors are allowed to create labels of their choice and associate them with their topic files. However, this can lead to many variations of a same label, for example one could have "Release 1.0", "Release-1.0", "release 1" labels for identifying the same stage of a topic. To avoid such inconsistent labeling in the system, you can create a predefined list of labels that authors would then be allowed to choose from. Having consistent labeling helps in better management of files in your system.

Using the version label configuration, you can upload a list of valid labels for your organization. Download the default label.json file and modify it as shown below:

```
{
"label1":"Draft",
"label2":"PM-Review",
"label3":"Engg-Review",
"label4":"QE-Review",
"label5":"Ready for Loc",
"label6":"Ready for Publish"
}
```

In the above example, the "label1" is the identifier for the label sequence and it is appended by the label that is displayed to the authors wherever a label is required. Save this file and upload it in the XML Content Version Labels section.

>[!IMPORTANT]
>
> For folder-level configurations to take effect, users would need to select the profile under their User Preferences in the Web Editor.

**Rootmap**

If your authors work with a specific root map, then you can browse to and select that rootmap here. Note that you can define the rootmap only for a folder-level profile.
