---
title: Create a bulk activation map collection
description: Learn how to Create a bulk activation map collection
exl-id: 7d17fb37-9486-4a3b-a421-08e279c95b6c
---
# Create a bulk activation map collection {#id214GG0E90EV}

To create a bulk activation map collection, perform the following steps:

1.  Select **Guides** from the list of tools.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Click on the **Bulk Publish Dashboard** tile.

    For the fist time, a blank collections page is displayed. If you have created bulk activation collections earlier, then they are shown on this page.

1.  Click **Create**.

1.  Enter a title for your bulk activation map collection and click **Create**.

    A Success message is displayed on creation of the bulk activation map collection.

1.  Click **Open** on the Success message.

1.  Click **Edit** and then click **Add Maps**.

1.  Locate and add the DITA maps that you want to add to the bulk activation map collection.

    By default, all the presets and locales associated with the map gets added automatically.

1.  Select the desired output by turning the sliding button on or off.

     You can choose multiple output presets across available locales.

1. Click **Done**.

    The DITA map files are added to your bulk activation map collection.

    ![](images/bulk-activation-collection-created.png){width="800" align="left"}


The Maps and Presets tab presents information in the following columns:

-   **Map**: Shows the title of the DITA map file.
-   **Map Path**: Shows the complete path of the DITA map file.

-   **UUID**: Shows the unique identifier associated with the file.

-   **Language**: Shows the language code of the DITA map.
-   **Preset**: Shows the title of the output preset configured on the map file. It also displays the icon based on the type of output preset. 

    >[!NOTE]
    >
    > The small ![](images/global-preset-icon.svg) icon indicates a folder profile level preset.
-   **Modified**: Indicates if the DITA map is updated after last publication. Based on this information, you can decide if you want to activate the output for this DITA map or not.
-   **Generated**: Shows the date and time of the last generated output.
-   **Published**: Shows the date and time of the last published \(or activated\) output. If you click on the link, the Activation Results page is displayed with information about the root path where the content is activated.


The following filtering options are available on the left panel:

-   **Modified**: You can select Yes or No. If you select yes, only the modified DITA maps are shown. A modified map is a map that has been generated since it was last published.
-   **Preset**: Select a preset for which you want to filter out the map files. For example, if you choose *AEM Site* preset, then only those maps are shown that have the *AEM Site* output preset configured on them.
-   **Language**: You can select any of the available language codes and display only the selected language in the Maps and Presets tab.

-   **Filter:** The lest rail shows the following filters:
-   **Maps and Presets** table: The Maps and Presets table shows has the following columns:

**Parent topic:**[Bulk Activation of published content](conf-bulk-activation.md)
