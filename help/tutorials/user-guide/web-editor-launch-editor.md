---
title: Launch the Web Editor
description: Learn how to Launch the Web Editor
exl-id: f02f9612-7aaa-42ea-bad3-c44d23b5d034
---
# Launch the Web Editor {#id2056B0140HS}

You can launch the Web Editor from the following locations:

-   [AEM Navigation page](#id2056BG00RZJ)
-   [AEM Assets UI](#id2056BG0307U)
-   [DITA map console](#id2056BG090BF)

The following sections cover the details of how you can access and launch the Web Editor from various locations.

## AEM Navigation page {#id2056BG00RZJ}

When you log into AEM, you are shown the Navigation page:

![](images/web-editor-from-navigation-page.png){width="800" align="left"}

Clicking the **Guides** link takes you directly to the Web Editor.

![](images/web-editor-launch-page.png){width="800" align="left"}

As you have launched the Web Editor without selecting any file, a blank Web Editor screen is shown. You can open a file for editing from AEM repository or your Favorites collection.

-  Click the Guides icon (![](images/aem-guides-icon.png) ), to go back to the AEM Navigation page. 

-  The **Close** button  takes you to a destination based on your setup: 



    <details>
        
    <summary> Cloud Services </summary>

    If you are using Cloud Services, click the **Close** button  to go back to the AEM Navigation page.
    </details>

    <details>

    <summary> On-Premise </summary>

    If you're using AEM Guides On-prem Service (4.2.1 and later), click the **Close** button on the right to go back to your current file path in the Assets UI.

    </details>

## AEM Assets UI {#id2056BG0307U}

Another location from where you can launch the Web Editor is from the AEM Assets UI. You can select one or more topics and open them directly in the Web Editor. To open a topic in the Web Editor, follow these steps:

1.  In the Assets UI, navigate to the topic that you want to edit.

    >[!NOTE]
    >
    > You can also see the UUID of the topic.

    .

    ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

    >[!IMPORTANT]
    >
    > Ensure that you have the read and write permissions on the folder that contains the topic you want to edit.

1.  To get an exclusive lock on the topic, select the topic and click **Check Out**.

    >[!IMPORTANT]
    >
    > If your administrator has configured the **Disable Edit Without Checkout** option, then you must check out the file before editing. If you do not check out the file, you will not be able to see the edit option.

1.  Close the asset selection mode and click the topic that you want to edit.

    The topic's preview is displayed.

    You can open the Web Editor from the List view, Card view, and the Preview mode.

    >[!IMPORTANT]
    >
    > If you want to open multiple topics for editing, select the desired topics from the Asset UI and click Edit. Ensure that your browser does not have pop-up blocker enabled, else only the first topic in the selected list is opened for editing.

    ![](images/edit-from-preview_cs.png){width="800" align="left"}

    If you do not want to preview a topic and want to open it directly in the Web Editor, then click the Edit icon in the quick action menu from the card view:

    ![](images/edit-topic-from-quick-action_cs.png){width="800" align="left"}

1.  Click **Edit** to open the topic in the Web Editor.

    ![](images/edit-mode.png){width="800" align="left"}


## DITA map console {#id2056BG090BF}

To open the Web Editor from DITA map console, follow these steps:

1.  In the Assets UI, navigate to and click the DITA map file that contains the topic you want to edit.

    The DITA map console is displayed.

1.  Click **Topics**.

    A list of topics in the map file is displayed. The UUID of topics is displayed below the topic title.

1.  Select the topic file that you want to edit.

1.  Click **Edit Topic**.

    ![](images/edit-topics-map-console_cs.png){width="800" align="left"}

1.  The topic is opened in the Web Editor.

    >[!IMPORTANT]
    >
    > If your administrator has configured the **Disable Edit Without Checkout** option, then you must check out the file before editing. If you do not check out the file, then the document opens in the editor in read-only mode.


**Parent topic:**[Work with the Web Editor](web-editor.md)
