---
title: Bulk tagging of DITA content
description: Learn how to Bulk tagging of DITA content
exl-id: 0e855575-e62f-4dc7-869c-7fd3ec61ffdb
---
# Bulk tagging of DITA content {#id179SG0TN05Z}

Tags allow you to group or classify content within your content repository and also in the published output. If you have applied tags on your content, you can easily find related topics within a DITA map that can help you to authoring content. With the published output, end users will be able to locate the right content faster with proper tags in place.

AEM Guides allows you to tag DITA content in a few clicks. You can use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or on a sub-map. Or, you can also apply tags on an individual topic. Tagging is the native feature in AEM, you can find more details about creating and managing tags in the [Administering Tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) section in AEM documentation.

By default, AEM Guides does not grant read access to any user on the folder where all tags in the AEM repository are stored. To use tags defined in the AEM repository, you must ask your system administrator to grant access on the folder where the tags are stored.

## Apply bulk tags 

Use the bulk tagging feature to apply multiple tags at once. Perform the following steps to apply tags to your topics in a DITA map:

1.  In the Assets UI, navigate to and click on the DITA map file.

    The DITA map console appears showing the list of Output Presets available to generate output.

1.  Click **Topics**.

    A list of topics available in the DITA map are displayed. The UUIDs of topics' is shown below the topic title.

1.  Select the topics or sub-map on which you want to apply tags.

    ![](images/apply-tags-uuid.png){width="650" align="left"}
    

    >[!NOTE]
    >
    > The above screenshot shows a sub-map selected and expanded. On selecting the sub-map, all the topics under the sub-map are also selected.

1.  Click **Apply Tags**.

    The Select Tags dialog appears.

1.  Select one or more tags that you want to apply on the selected topics.

1.  Confirm your selection.

    The selected tags are applied on the topics and shown next to the topic title.

    >[!NOTE]
    >
    > After adding tags to your topics, if you move or delete a topic, then the tags for those topics are also removed. However, that topic remains in the map until you remove it.


## Apply tags on an individual topic 

Perform the following steps to apply tags to an individual topic:

1.  In the Assets UI, navigate to and select the topic file on which you want to apply tags.

1.  In the toolbar, click **Properties**.

    The topic's properties page appears.

1.  In the Basic tab, click the Browse icon next the **Tags** field.

1.  Select one or more tags that you want to apply on the selected topic.

1.  Confirm your selection.

1.  Click **Apply Tags**.

    The selected tags are applied on the topic and shown in the Tags field.

1.  Click **Save & Close**.


## Remove tags 

As per your business needs, you can change the tagging information for any DITA topic. You can easily remove all tags at once or remove only those tags that are no valid on the topic.

Perform the following steps to remove all tags from one or more topics:

1.  In the Assets UI, navigate to and click on the DITA map file.

    The DITA map console appears showing the list of Output Presets available to generate output.

1.  Click **Topics**.

    A list of topics available in the DITA map are displayed.

1.  Select the topics from which you want to remove tags.

1.  Click **Remove Tags**.

    >[!NOTE]
    >
    > If the Delete Tags icon is not visible, ensure that you have not enabled the Hide Tags feature.

1.  On the Confirm Delete dialog, click **OK** to remove tags from the selected topics.


## Show or hide tags 

If you have a long list of tags applied on your topics, then you might find it a bit cumbersome to navigate. You can easily hide tags in from your DITA map console view by clicking on the Hide Tags icon. Similarly, when the tags are not visible, clicking on the Show Tags reveals all tags.

**Parent topic:**[Manage metadata](manage-metadata.md)
