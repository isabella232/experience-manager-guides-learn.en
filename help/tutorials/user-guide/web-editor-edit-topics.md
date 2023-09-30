---
title: Edit topics in the Web Editor
description: Learn to edit topics in the web editor. Know about various editing features to modify your topic files in AEM Guides.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
---
# Edit topics in the Web Editor {#id2056B040VUI}

The Web Editor comes with a range of editing features that let you easily create or modify your topic files. Broadly, you would perform the following steps to edit a topic in the Web Editor.

>[!IMPORTANT]
>
> If you encounter an application error while working on the Web Editor, refresh the page to continue working.

1.  To make changes in your topic, click within the text boundary of the required element and start making edits.

1.  To insert a specific element, click at the end of the element after which you want to insert the new element and click the required element icon in the toolbar. You can also use the keyboard shortcut `Alt+Enter` to invoke the **Insert Element** popup.

    A list of element appears that can be used in the topic. AEM Guides does an intelligent placing of elements as per their valid location in the topic.

    >[!NOTE]
    >
    > You can also choose which icon to be displayed in the toolbar by configuring the `ui_config.json` file located at - `/etc/designs/fmdita/clientlibs/xmleditor/`. For more information about customizing features, contact your system administrator.

1.  Once you have finished editing your document, click **Save**.

    >[!NOTE]
    >
    > If you do not wish to commit changes into AEM repository, click **Close**, and then click **Close Without Saving** in the Unsaved Changes dialog.

    **Refresh browser while editing the files**
    AEM Guides provides the support to refresh the browser while you edit your content in the Web Editor. This feature helps you continue editing content in case you encounter an application error while working. If you hit the browser refresh while one or more files with unsaved changes are opened for editing, you are warned that the unsaved changes may be lost. You are given an option to cancel the refresh operation and save your files to preserve your changes.

    Even on refreshing the browser, the views of the left and the right panel are retained in the Web Editor. For example, the active topic in the Repository panel is opened again. The map panel is retained along with the previously opened map.

    The active topic or DITA map is reopened in the content editing area.

    The right panel is also reopened and displays the same view as before the refresh.

    **Working copy indicator**
    AEM Guides provides the working copy indicator which shows whether the current \(working copy\) of file is in sync with the saved version or not. If you have made any changes to your current copy and have not saved your file, a \* mark appears along with the title on the topic's file tab. This indicator acts as a reminder to save your changes and disappears when you save your file.

    ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

    AEM Guides also indicates if the last saved \(working\) copy of the file is in sync with the saved version or not. If you have some unsaved changes between the working copy and the last saved version, a \* mark appears along with the version information shown in the right top corner of the topic's file tab. This indicator acts as a reminder to save and create a version from your current \(working\) copy of the file.

    ![](images/version-update-indicator.png){width="550" align="left"}


**Parent topic:**[Work with the Web Editor](web-editor.md)
