---
title: DITA map report from the Web Editor
description: Learn how to DITA map report from the Web Editor
exl-id: b1011cec-6374-4026-bf1c-54a1981c760e
---
# DITA map report from the Web Editor {#id231HF0Z0NXA}

AEM Guides comes with a feature in the Web Editor that enables you to check the overall integrity of your references and generate reports for them.

You can view the topic list, manage the metadata of all references, and view the multimedia list for the current map from the **Reports** tab in the Web Editor.

## Generate a CSV from the Topic List view 

The **Topic List** view provides detailed information about your topics, such as the reference type, document state, and author.

You can create a report of the topics by performing the following steps:

1.  In the **Repository** panel, open the DITA map file in Map View.
1.  Click the **Manage** tab.
1.  Double-click **Topic List** on the left. The list of topics present in the DITA map is displayed.

    ![](images/web-editor-topiclist-panel.png){width="800" align="left"}

1.  From the **Filters** Panel you can filter your topics based on the **Reference type** \(direct or indirect\), **Document State** \(the current state of your topics. For example if your topics are in Edit, In-Review, or Reviewed state, these are listed\) or the **Author** of the topic.

1.  You can also use the following topic filtering options to choose to display the following columns in the list:

    -   **Topic** The title of the topic is specified in the DITA map. You can click the topic to edit it.
    -   **File Name** Name of the file.
    -   **UUID** The universally unique identifier \(UUID\) of the file.
    -   **File Location** The complete path of the topic.
    -   **Reference Type** The type of reference – direct or indirect.
    -   **Document State** The current state of the topic.
    -   **Author** The user who worked last on the topic.
    -   **Parent Map** The list of all maps where the topic is directly referenced.
    >[!NOTE]
    >
    > Click **Refresh** to get a fresh list of topics and see any change in your map file or if any reference within your topic file is updated.

1.  Click **Download CSV** to download the current snapshot of the topics in the DITA map. The CSV contains the selected columns and the topics filtered in the **Topic List** view. You can then open this topic list CSV file in any CSV editor.

**Manage metadata in bulk from the Metadata report**

AEM Guides allows you to tag DITA content from the Web editor. You can apply tags on an individual topic or use the bulk tagging feature to apply multiple tags on multiple topics, a DITA map, or on a sub-map. You can also change the document state of all selected topics to the next possible common document state.

## View metadata 

To view the metadata of your references in the current DITA map, perform the following steps:

1.  In the Repository panel, open the DITA map file in Map View.
1.  Click the **Manage** tab.
1.  Double-click **Metadata** on the left. The metadata list of all the references in the DITA map is displayed. This includes the media references also.

    ![](images/web-editor-metadata-panel.png){width="800" align="left"}

1.  From the **Filters** panel you can filter your topics based on the **Document State** \(the current state of your topics. For example if your topics are in Edit, In-Review, or Reviewed state, these are listed\), **References** \(direct or indirect\), **File Type** \(Map, Topic, and Image\) of the reference.
1.  You can also choose to view only the **Files with no tags** or also choose specific tags from the **Tags** filter to view the files associated with them.
    1.  You can also use the following topic filtering options to choose to display the following columns in the metadata list:
        -   **Title** \(selected by default\) The title of the referenced file is specified in the DITA map. You can click the file to edit it.You can also click and play an audio or video file in the Web Editor. You can change the volume or the view of the video. In the shortcut menu you also have the options to download, change playback speed, or view picture in picture.

            >[!NOTE]
            >
            > A checked-out icon also appears near the title of a checked-out file. You can hover over the icon to view the name of the user.

        -   **File Name** The name of the file.
        -   **File Location** The complete path of the file.
        -   **Tags** \(selected by default\) Tags applied on the file.

            >[!NOTE]
            >
            > By default, you can see two tags for a file. To view more tags, click **Show More**. Click **Show Less** to contract the list again.

        -   **Reference Type** The type of reference – direct or indirect
        -   **Document State** \(selected by default\) The current state of the reference file.
        -   **File Type** \(selected by default\) Type of the source file. The available options are Map, Topic, and Image.
        -   **Checked Out by** The user who has checked out the file.
1.  Click **Download CSV** to download the current snapshot of the references in the DITA map. The CSV contains the selected columns and the references filtered in the Topic List view. You can then open this metadata CSV file in any CSV editor.

**Update metadata**

1.  To update metadata, select the files for which you want to update.

    >[!NOTE]
    >
    > You cannot select any checked-out files. A checked-out icon also appears near the title of a checked-out file. You can hover over the icon to view the name of the user.

1.  Select **Manage** from the top.

    ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1.  If you want to add any new tags, select new tags from the dropdown list to apply them to all selected topics. You can also delete any tag by clicking the cross icon near the tag.

    >[!NOTE]
    >
    > The common tags applied on all the selected topics are listed.

1.  Select a new document state if you want to change the document state of all the selected references. The dopdown displays the common possible state for all selected topics. For example, if the current state of your topics is In-Review, then you can see Draft, Approved, or Reviewed state.
1.  Click **Update** to update the metadata. A confirmation message is displayed for the metadata whether it is updated successfully or has any failed updates. You also click **Download Report** to download the metadata CSV from the confirmation dialog. This CSV contains the details of the update status for the selected references.

## Generate a multimedia report 

The **Multimedia**report provides detailed information about the multimedia used in your map, such as the title, type \(audio, video, and images\), files in which multimedia is used, and the reference type of the files, in which they have been used. You can also view the UUID and the location of the multimedia within the repository. You can create a report of the multimedia by performing the following steps:

1.  In the **Repository** panel, open the DITA map file in Map View.
1.  Click the **Manage** tab.
1.  Double-click **Multimedia** on the left. The list of multimedia present in the DITA map is displayed.
1.  From the **Filters** panel you can order the list by multimedia or by the names of used in references.

    -   When you order by **Multimedia**, the****name of the multimedia is displayed in the first column and then the names of all references in which they have been used, are displayed in another column on the same row. For example, the following screenshot shows the multimedia WarmCoolForC.gif in the first column and three references in which it is used, are displayed in the third column on the same row.

        ![](images/multimedia-report-file-order.png){width="650" align="left"}

    -   If you order by **Used In** column, you will see the transposed view wherein the names of the references in which multimedia have been used are listed in the first column while the multimedia names are listed in another column on separate rows. For example, the following screenshot shows the names of three references \(Adjust the seat temperature, Change the seat temperature display, and Crew area\) in the first column and the multimedia WarmCoolForC.gif is displayed in the third column on three separate rows.

        ![](images/multimedia-report-used-in-order.png){width="650" align="left"}

1.  You can filter your multimedia based on the **Multimedia Type**, and **Reference Type**. The list of multimedia files is displayed based on your selection in the drop-down. For example, you can choose to display only the audio references in your DITA map, and a file shows only the audio references used in it.

    >[!NOTE]
    >
    > Depending on the type of multimedia used in your map, Image, Video, and Audio are listed in the **Multimedia Type** drop-down, and Direct or Indirect are listed in the **Reference Type** dropdown.

1.  You can also use the following filtering options to choose to display the following columns in the list:

    -   **Multimedia** \(selected by default\) The title of the multimedia is specified in the DITA map. You can click the multimedia to edit it.
    -   **Multimedia Location** The complete path of the multimedia.
    -   **Multimedia UUID** The universally unique identifier \(UUID\) of the file.
    -   **Multimedia Type** \(selected by default\) Type of the multimedia. The available options are Audio, Video, or Image.
    -   **Used In** \(selected by default\) The references in which the multimedia has been used. You can click the reference to edit it.
    -   **Reference Type** \(selected by default\) The type of reference - direct or indirect.
    >[!NOTE]
    >
    > Click **Refresh** to get a fresh list of multimedia and see any change in your map file or if any multimedia within your DITA map is updated.

1.  You can also click and play an audio or video file in the Web Editor. You can change the volume or the view of the video. In the shortcut menu you also have the options to download, change playback speed, or view picture in picture.

    ![](images/video-web-editor.png){width="800" align="left"}

1.  Click **Download CSV** to download the current snapshot of the multimedia in the DITA map. The CSV contains the selected columns and the multimedia filtered in the **Multimedia** view. You can then open this multimedia CSV file in any CSV editor.


## View and fix the broken links

The **Broken Links** is a useful report which provides you with the details of the broken links present in your current map. You can view the broken links, which can be for DITA topics, multimedia file references, content key references, and so on. You also have the ability to fix the broken links here itself.
The report provides detailed information such as the broken link, link type, files in which reference is used, and the type of files they have been used in. 
You can view the report for broken links by performing the following steps:
1. In the **Repository** panel, open the DITA map file in Map View.
1. Click the **Manage** tab.
1. Double-click **Broken Links** on the left. The list of broken links or references present in the DITA map is displayed.
1. From the **Filters** panel you can order the list by links or by the names of used in references.

    – When you order by **Broken Link**, the paths of the broken links are displayed in the first column and then the names of all references in which they have been used, are displayed in another column on separate rows. If the same broken link is used in multiple files, then they are displayed on one row and are shown as grouped or sub-rows. For example, the following screenshot shows three broken links in the first column and the reference in which they are used, `TestMap.ditamap` is displayed in the third column on three separate rows.
    ![](images/broken-link-report.png){width="800" align="left"}
 
    – If you order by **Used In** column, you will see the transposed view wherein the names of the references in which the broken links have been used are listed in the first column while the broken links are listed in another column on the same row. For example, the following screenshot shows the reference (in which the broken link is used) `TestMap.ditamap` in the first column and the broken links are displayed in the third column on the same row.
    ![](images/broken-link-filter-usedin.png){width="800" align="left"}
1. You can filter your broken links based on the **File Type** and **Link Type**. The list of broken links is displayed based on your selection in the drop-down. For example, you can choose to display only the content references in your DITA map, and a file shows only the content references used in it.

    Depending on the type of references used in your map, File reference, Key reference, Content Reference, Content Key Reference, Image Reference, and Multimedia File Reference are listed in the **Link Type** drop-down, and **DITA Topic** or **DITA Map** are listed in the **File Type** dropdown.
1. You can also use the following filtering options to choose to display the following columns in the list:

    – **Broken Link** (selected by default) The path of the broken link is specified in the DITA map. 

    – 	**Link Type** (selected by default) The type of the links. The available options are Content Key Reference, Content Reference, DITA Topic, File Reference, Image Reference, Key reference, and Multimedia File Reference.

    – 	**Used In** (selected by default) The references in which the broken link has been used. You can click the reference to view it in author mode.

    – 	**File Type** (selected by default) The type of reference – DITA Map or DITA Topic.
    Click **Refresh** to get a fresh list of broken links and see any change in your map file or if any broken link within your DITA map is updated.
1. 	You can click on the **Fix link** icon (![](images/fix-broken-link.svg)) to fix the broken link. 
    >[!NOTE] 
    >
    > Hover over the broken link path under the Broken Link column to view the Fix link (![](images/fix-broken-link.svg))  icon.

    You can fix a link in both views- when you have ordered by **Broken Links** or by **Used In**.
    >[!NOTE]
    >
    > When you fix a broken link while you have ordered by Broken Links, the link will be fixed in all the files where it is used (which are grouped in a single row).
1. You need to update the required reference details in the **Update Link** dialog. The details required in Update Link dialog would depend on the type of reference.

    
    Once you fix a link, it is not displayed under the list of broken links. Instead, you can see it under the Topic List or Metadata. 



1. 	Click **Download CSV** to download the current snapshot of the broken links in the DITA map. The CSV contains the selected columns and the broken links filtered in the Broken Links view. You can then open and view this CSV file in any CSV editor.


**Parent topic:**[Reports](reports-intro.md)
