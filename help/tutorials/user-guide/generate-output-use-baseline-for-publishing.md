---
title: Work with Baseline
description: Know the use of Baselines in AEM Guides. Learn how to create, view contents, edit, duplicate, remove, add labels, and export translated Baselines.
exl-id: dcafab53-c388-48c3-9455-e4251cdda17d
---
# Work with Baseline {#id1825FI0J0PF}

The Baseline feature allows you to create a version of your topics and assets that can then be used for publishing or translation. For example, if your DITA map has `topicA` and `imageA`, you can create a Baseline to use the 3rd version of `topicA`, but the 4th version of `ImageA`. Once you have a Baseline in place, you can publish or translate topics of different versions with a single click.

Selecting a Baseline is optional for output presets and a DITA map can have more than one Baseline. However, each output preset within a DITA map can be associated with only a single Baseline. If no Baseline is specified at the time of publishing, then the output is published using the latest version of the content.

Similarly, selecting a Baseline to translate content is optional. However, if you choose to translate content using a Baseline, the contents of the Baseline are also saved along with the translated copies. You can then use the translated Baseline to perform further operations like share it with external publishers or archive it. For more information about exporting a translated Baseline, see [Export translated Baseline](#id196SE600GHS).

>[!TIP]
>
> See the *Baseline* section in the Best practices guide for best practices around working with Baselines.

Your administrator can configure the Baseline tab on the map dashboard. For more details, see *Configure Baseline tab on the DITA map dashboard* section in the Installation and Configuration Guide.

You can access the Baseline feature by performing the following steps:

1.  In the Assets UI, navigate to and click on the DITA map file.
1.  Go to the **Baselines** tab.

In the Baselines tab, you can perform the following actions:

-   [Create a Baseline](#id195FI0I0MUQ)
-   [View contents of a Baseline](#id195FI0I0TLN)
-   [Edit, duplicate, or remove Baselines](#id195FI0I0YJL)
-   [Add labels to a Baseline](#id184KD0T305Z)

## Create a Baseline {#id195FI0I0MUQ}

You can create a Baseline with a specific version of the topics and referenced content available on a specific date and time, or with a label defined for a version of topics. You can individually specify the versions of selected topics in a Baseline so that each time you apply the Baseline in publish or translation workflow, the selected topics and their corresponding versions are included for output generation or translation.

Perform the following steps to create a baseline:

1.  On the Baselines page, click **Create**.
1.  Enter a name for the Baseline in **Baseline Name**.
    ![create a baseline](images/create-baseline.png){width="800" align="left"}
1.  In **Set the Version Based on**, select one of the following options:

    -   **Label**: Select this option to pick the topics according to the label applied to them. Enter a label to filter the list based on the entered string. From the filtered out list, you can choose a label to select topics and other assets having the specified label.

    When you select **Label**, you are also given an additional option to use the latest version of topics that do not have the specified label applied on them. If you do not select this option, and there's any topic or media file that doesn't have the specified label on it, then the baseline creation process will fail. For more information about adding labels, see [Use labels](web-editor-use-label.md#).

    -   **Version on** <*time stamp*\>: Picks the topics' version as on the specified date and time. Note that the time that you specify here corresponds to the timezone of your AEM server. If your server is at a different timezone, then the topics will be picked up as per your server's timezone and not your local timezone.

    Once you have selected a label or version as on date, then all referenced topics and media files within the map are selected accordingly. This selection of topics is not shown on the user interface, but it is saved in the backend.

    >[!NOTE]
    >
    >It is recommended not to use the **Browse All Topics** link when creating a baseline. 

1.  Click **Save**.

## View contents of a Baseline {#id195FI0I0TLN}

You can view the contents of an existing Baseline by clicking on the Baselines tab and selecting the desired Baseline version from the list. The Baselines page is divided into three parts – DITA map file, map's contents or topics, and the referenced content. If your map contains sub-maps, then the topics referenced from the sub-map are also displayed in the Content section. The various columns on the Baseline page are described below:

- **Name**: Lists the DITA map or topic's title or the name of the asset, such as the file name of an image.

- **Kind**: Lists the kind or type of asset in the map like DITA map, DITA topic, or image format.

- **Version**: Lists the version of the asset available in the Baseline.

- **Version Date and Time**: Lists the creation date and time of the asset for the selected version.

- **Latest**: Lists whether the latest version of the asset is used in the Baseline.

- **Parent Map**: If your map file contains sub-maps, then this column contains the name of the map in which a topic is referenced.

- **Label**: Lists the label\(s\) applied to the version of the topic.

- **Referenced By**: This column is available for the referenced content only. It indicates the parent topic of the referenced asset. In case an asset is referred by multiple topics, then the topics are separated by comas.

## Edit, duplicate, or remove Baselines {#id195FI0I0YJL}

**Edit Baselines**

Perform the following steps to edit an existing baseline:

1.  Select the Baseline and click **Edit**.
1.  Make the required changes in the baseline. You can change the name and version of the topic or referenced content.
1.  If you want to use a different version for one or more topics, then you can do so by manually selecting those topics. Click **Browse Topic**, select the topic for which you want to use a different version. From the Select a Version drop-down list for the selected topic, select a version of the topic that you want to use in the baseline and click **OK**.

    ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

    The information about the topic and it's selected version is stored in the backend. You can repeat this step to change the selected version for multiple topics.

1. To load all topics and media files referred from the DITA  map, click the **Browse All Topics** link. The UUID of topics and media files is also shown below the topic title or the \(media\) file name.

    >[!NOTE]
    >
    > If you have a very large set of files in your DITA map, with nested maps and topics, then clicking Browse All Topics could take some time to load all files.

    The contents of your map are presented in the three sections: the map file, Content \(topic references\), and Referred Content \(nested topics, maps, and other assets\). Once you have all the referenced content available, you can individually select the version of the topic that you want to use in your baseline.

    The **Version** drop-down list shows the available versions of the topics or the referenced content. For the referenced content, you have the option to choose a version automatically.

    If you choose **Pick Automatically** for the referenced content, the system automatically picks the version of the referenced content corresponding to the version of the content in which it is referenced. For example, let's say a topic A has a reference to an image B. When version 1.5 of topic A was created, the version of image B was 1.2 in the repository. Now, when a baseline is created with version 1.5 of the topic A with image B set to **Pick Automatically**, the system will automatically pick version 1.2 of image B.

    If you create a baseline using the labels, **Pick Automatically** is applied to the version of all referenced content.

    If the referenced content or assets \(topic, sub-maps, images, or videos\) are not versioned \(such as, newly uploaded content\), then creating a baseline will create a version for such files. However, if your files are versioned, then no incremental version is created for those files. This behavior is controlled by the auto-create version setting, which is enabled by default. This is also required for translating content wherein the translation process expects all files to have a version.

    >[!NOTE]
    >
    > If you want to specify a different version for any particular resource, you can do so by choosing the desired version from the **Version** drop-down list.
1.  Click **Save**.

**Duplicate Baselines**

Select the Baseline and click **Duplicate** to create a copy of an existing Baseline. Specify a different name for the baseline and choose the version number for the topics and referenced content and click **Save**.

**Remove Baselines**

Select the Baselines version and click **Remove** to remove a Baseline.

## Add labels to a Baseline {#id184KD0T305Z}

Adding labels to every single topic can be time consuming. AEM Guides provides a single-click mechanism of adding labels to multiple topics and referenced content in a DITA map.

Perform the following steps to add a label to multiple topics and referenced content in a DITA map:

1.  On the Baselines page, select a baseline containing the topics and referenced content on which you want to add a label.

    >[!NOTE]
    >
    > Ensure that your baseline does not have the latest version of any topic or asset. A label can only be added to a versioned topic or asset.

1.  Click **Add Labels**.

    ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1.  In the **Add Label** dialog, specify a unique label to associate with this baseline.

    If your administrator has configured pre-defined labels, then you are shown those labels in a drop-down list. You need to choose a label from the list.

1.  If you want to apply the label to topics referenced from the sub-maps, then select **Apply Label to Child Maps and Dependents** option.

    - Click **Add**.
        The specified label is added to the DITA map and the referenced topics and content.

        ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Export translated Baseline {#id196SE600GHS}

You can use Baseline for translating content. For example, you can create a Baseline for Version 1.1 that is ready for translation in French. In the Translation tab, you need to use Baseline to filter your content, then select the Baseline for Version 1.1 of your content. Using Baseline for translating content makes it easier for you to manage your content.

Once the content is translated, you can then export the translated Baseline for archival or sharing it with different teams in your organization. You must consider the following points before exporting a translated Baseline:

-   Exporting a Baseline is only possible after the content in the Baseline is translated. If you try to export a baseline for which the translation is not started or is not complete, then you will get an error.
-   You can only transfer Baseline for a version that is already translated. For example, if you have created a Baseline for version 1.1 of your content and the same is translated, you can export this baseline. However, if you have created a Baseline for version 1.2, which is not translated, you cannot export this Baseline.
-   If a Baseline is already exported, you can overwrite the existing baseline by selecting the *Overwrite Existing Baseline* option while exporting.

Perform the following steps to export a translated Baseline:

1.  Open the DITA map that contains the translated Baseline.

1.  In the **Translation** tab, expand the **Baseline** option available in the left rail.

    ![](images/export-baseline.png){width="800" align="left"}

1.  Select the **Use Baseline** option and choose the Baseline that you want to export.

1.  Click **Export Baseline**.

    The Export Status is displayed. If the process is successful, then you are shown a message mentioning the language for which the Baseline is exported. In case of a failure, the cause of failure is displayed.

    If you try to export the Baseline which is already exported, then also you are shown the Baseline creation failure message.

1.  \(Optional\) To export a Baseline which is already exported, select **Overwrite Existing Baseline** and then click **Export Baseline**.


**Parent topic:**[Output generation](generate-output.md)
