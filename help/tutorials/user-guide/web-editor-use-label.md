---
title: Use labels
description: Learn how to Use labels
exl-id: 3ea56d06-537f-4bfd-922d-df1f23e61a20
---
# Use labels {#id164JBG0M0T1}

AEM Guides allows you to add labels to different versions of a file. You can use these labels to specify the version that you want to include in a baseline for publishing. For more information about using labels to create a baseline, see [Work with Baseline](generate-output-use-baseline-for-publishing.md#).

For example, if you want to use *version 1.0* of a topic in *release 1.0* and *version 1.1* of the same topic in *release 2.0*, you can add *release 1.0* label on the *version 1.0* and *release 2.0* label on the *version 1.1*.

Once you have added the labels, you can create a baseline and specify which version of the topic should be included for publishing using that baseline. To see what version should be included or excluded in a baseline, you can use the Version History option.

## Add a label 

Perform the following steps to add a label to your topic:

1.  In the Assets UI, select a topic
1.  Click the left rail selector icon and select **Version History**.
1.  In the Version History, click a version where you want to add a label.

1.  Enter a label for the selected version and press Enter. For example, *2.6 Release*.

    >[!NOTE]
    >
    > You cannot add the same label to the different versions of a topic. However, you can add multiple labels to the same version of a topic.

    The labels are displayed in the Version History of the selected topic. The following screenshot displays the labels *x.x Release* and *User Guide* added to the highlighted version of the topic.


![](images/labels.png)

>[!NOTE]
>
> Using a baseline, you can add a label to multiple topics. For more information about adding labels using baseline, see [Add labels to a Baseline](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

## Delete a label 

Perform the following steps to delete a label:

1.  In the Assets UI, select a topic that has a label added to it.
1.  Click the left rail selector icon and select **Version History**.

    In the Version History, you will see all the versions of a topic and the labels attached to them. The following image shows an example of different versions of a topic and one version has labels added to it.

    ![](images/labels.png)

1.  Click the delete button \(**X**\) to delete the label.

    ![](images/delete-labels.png)


**Parent topic:**[Work with the Web Editor](web-editor.md)
