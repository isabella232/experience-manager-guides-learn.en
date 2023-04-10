---
title: Download files 
description: Learn how to Download files 
---

# Download files {#id216MC0H0BE8}

You can download assets including DITA and non-DITA files. There are multiple ways in which you can download assets, some methods are native to AEM and others are supported by AEM Guides. For native AEM assets download information, see [Download assets from Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) in AEM documentation. The following section explains the mechanism of downloading files via DITA map console in AEM Guides.

## Export a DITA map file 

Once you have the DITA map file in the AEM repository, you can download the map file along with its dependents. This gives you the flexibility to share the complete map file for offline editing, validation, review, or simply creating a backup.

Perform the following steps to download a DITA map file along with its dependent files:

1.  In the Assets UI, navigate to the DITA map that you want to download.

1.  Click on the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to see a list of topics available in the DITA map.

1.  In the main toolbar, click **Download Map**.

    The Download Map dialog appears.

    ![](images/download-map.png)

1.  Click **Download**. In the Download Map dialog, you can choose the following options:

    -   **Use Baseline**: Select this option to get a list of Baselines created for the DITA map. If you want to download the map file and its contents based on a specific Baseline, select the Baseline from the drop-down list. For more details about working with Baselines, see [Work with Baseline](generate-output-use-baseline-for-publishing.md#).
    -   **Flatten File Hierarchy**: Select this option to save all referenced topics and media files in a single folder.
    >[!NOTE]
    >
    > You can also download the map file without selecting any option. In that case, the last persisted version of the referenced topics and media files are downloaded.

1.  After you click the **Download** button, the map download request is queued. You will receive the following notification once the map is ready to download.

    ![](images/download-map-prompt.png)

    -   Click **Download** to download the map file in.zip format.

    -   Click **Download Later** to download the map file at a later time. The download link can be accessed from the AEM notification Inbox. Click the generated map notification in the Inbox to download the map in .zip format.

    >[!NOTE]
    >
    > By default, the downloaded maps remain for five days in the AEM notification Inbox.

![](images/download-map-inbox.png)

Once the map is downloaded, you can select the map and use the Open icon on the top to open the selected report.

**Parent topic:**[Manage content](authoring.md)

