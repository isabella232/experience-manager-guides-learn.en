---
title: Manage Global and Folder Profile output presets
description: Learn how to create, edit, rename, duplicate, and delete global and folder profile output presets as administrative users in AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
---
# Manage Global and Folder Profile output presets {#id22BLJ0D0V1U}

The Global and Folder Profile presets are only available to folder-level administrative users.

As an administrator, AEM Guides allows you to create and manage output presets for the Global and Folder Profiles. Then you can easily use these output presets to generate output for all maps that are related to that Global or Folder Profile.

Perform the following steps to create an output preset for the Global and Folder Profiles:

1.  Select the DITA map for which you want to create an output preset.
1.  Select the **Edit Topics** option from the **Options** menu of the map file. The map file is opened for editing in the Web Editor.
1.  In the **Output** tab, select the + icon to create an output preset for your DITA map.

    ![](images/add-global-output-preset.png){width="350" align="left"}

1.  Enter the following details in the **Add preset** dialog:
    -   Type
    -   Name
    -   Target \(for Knowledgebase preset\)
1.  Select the **Add to folder profile** check box to create an output preset for the related folder profile and then click **Add**. The preset is created, and it appears under the **Output** tab of all related maps. \( ![](images/global-preset-icon.svg)\) icon indicates a folder profile level preset.
1.  Enter the configuration details. For more details on output presets, view [Understanding the output presets](./generate-output-understand-presets.md).

    >[!NOTE]
    >
    > These presets added to the folder profile are independent of the maps, so the map specific configurations are not present for these presets.

1.  You can select the **Generate Preset** icon at the top to generate the output for the maps related to the created output preset. You will see the status of the output generation process. To view the output, hover the mouse pointer over the topic and click **View Output**.

>[!NOTE]
>
> AEM Guides also provides an out-of-box PDF output preset to generate the output for your DITA maps.

**Other operations from the Options menu**

You can also perform the following operations on the preset from the Options menu:

-   Select the preset as default pdf preset. Then the selected preset would be used as the default preset to generate the PDF output using the **Download as PDF** option for a map.
-   **Edit**, **Rename**, **Duplicate**, or **Delete** an existing output preset from the **Options** menu.

>[!NOTE]
>
> When an output preset in Global and Folder Profiles is deleted, it will reflect in all related maps and will not appear under the **Output** tab.

**Parent topic:**[Work with the Web Editor](web-editor.md)
