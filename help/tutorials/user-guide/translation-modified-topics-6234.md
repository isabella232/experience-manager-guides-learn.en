---
title: Translate modified topics
description: Learn how to Translate modified topics
exl-id: 48b868c3-27ec-4641-b40d-17a641be7497
---
# Translate modified topics {#id16A5A0B6072}

If you make changes in some of the topics, then those topics require re-translation. You can keep track of modified topics from DITA map. From the source language copy folder, click the DITA map file and click the Translation tab. You can see the status of each topic whether it requires re-translation or not.

Perform the following steps to send a modified topic for re-translation:

1.  Click the DITA map file from the source language copy folder.

1.  Click the **Translation** tab.

1.  In the **Filter** panel on the left, select the **Translate Languages** that you want to check the status for and click **Done**.

    You can see the translation status for each topic. The topics that have another revision of topic available than what was sent for translation, show an **Out of Date** status.

    >[!NOTE]
    >
    > The translation workflow compares the last saved revision of the topic file in the source language folder with the translated version.

    If you click the arrow to see further details. you can see the particular language copy that is out of date.

    ![](images/out-of-sync-uuid.png){width="800" align="left"}

1.  Click the check box to select the topics that you want to send for re-translation.

    When you select an out of sync date, the **Create/Update Language Copies** option appears in the References panel and the **Dismiss Out of Sync Status** button above the **Filter** icon.

    You can use the **Dismiss Out of Sync** button to override the Out of Date status for the topics in the DITA map. For example, if you made some changes in the English version of the topic that does not need translation, you can use this button and change the Out of Date status for the selected topic.

    >[!NOTE]
    >
    > If you click the **Dismiss Out of Sync Status** button, it sets the topic status to Up to Date for the selected Out of Date topics.

1.  Click **Update Language Copies** and configure the translation job.

1.  You can choose to create a new translation project or add topics to an existing translation project. Provide the required details to configure the translation project.

1.  Click **Start**.

    A confirmation message is displayed showing that the topic has been sent for translation.

1.  Navigate to the translation project in the Project console. A new translation job card is created in the folder. Click the ellipsis to see the assets of the folder.

    ![](images/incremental-job.PNG){width="300" align="left"}

1.  To start the translation, click the arrow on the translation job card and select **Start** from the list. A message notifies that the job has started.

    You can also view the status of the topic being translated when you click the ellipsis at the bottom of the translation job card.

    >[!NOTE]
    >
    > If you are using Human translation service, then you need to export the content for translation. Once you have the translated content, then you need to import it back into the translation project.

1. After the translation completes, the status changes to **Ready to Review**. Click the ellipsis to see topic details and do one of the following from the toolbar:

    -   Click **Reveal in Assets** to see and verify the translation.

    -   Click **Accept Translation** if you think that the changes have been translated correctly. A confirmation message is displayed.

    -   Click **Reject Translation** if you think that the job needs to be re-done. A rejection message is displayed.

    >[!NOTE]
    >
    > It is important to Accept or Reject the translated asset, else the file stays in the temporary location and does not get copied to DAM.

1. Navigate back to the DITA map file in the source language folder in Assets UI. The re-translated topics are now in sync.


**Parent topic:**[Translate content](translation.md)
