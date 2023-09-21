---
title: Manage files and folders
description: Manage files and folders in AEM Guides. Learn how to copy and paste, drag and drop, delete, move files and folders in bulk, and search DITA content.
exl-id: e7810b06-f49f-467a-b987-a5e6f731d4cf
---
# Manage files and folders {#id2116G0L08XA}

This section explains how AEM Guides handles the basic file operations, such as copy, paste, drag-and-drop, and delete files. The following scenarios are possible:

## Copy and paste files 

**If the file has human readable filename**

-   *If the file with the same name does not exist in the destination folder*: A new copy of the file is created and a UUID is also assigned to it. Here, the file name is same as the original file name.
-   *If the file with the same name already exists in the destination folder*: A new copy of the file is created with a suffix \(like filename0.extension\). A UUID is also assigned to the newly created file.


**If the filename is based on a UUID pattern**

-   *If the file with the same name does not exist in the destination folder*: A new copy of the file is created and a new UUID is also assigned to it at the new location. Here, the file name is same as the UUID.
-   *If the file with the same name already exists in the destination folder*: A new copy of the file is created and a new UUID is also assigned to it. The file name is same as the UUID.


## Copy and paste folders 

**Copy and paste folder at the same location**

-   *The folder has files with human readable filenames*: A new copy of the folder is created with a suffix \(like foldername0\). A new UUID is also assigned to the files within the folder. However, there is no change in the file names.

-   *The folder has files with filenames based on a UUID pattern*: A new copy of the folder is created with a suffix \(like foldername0\). A new UUID is also assigned to all files within the new folder. The file names are also changed; the file names are same as the new UUID.


**Copy and paste folder at different location**

-   *The folder has files with human readable filenames*: A new copy of the folder is created and a new UUID is also assigned to all files within the folder at the new location. Here, there is no change in the folder or file names.

-   *The folder has files with filenames based on a UUID pattern*: A new copy of the folder is created with the same name as the original folder. A new UUID is also assigned to all files within the new folder. The file names are also changed; the file names are same as the new UUID.


## Drag-and-drop files 

**Drag-and-drop with human readable filenames**

-   *Drag-and-drop at the same location*: You are given the options to **Overwrite Existing File\(s\)**, **Keep Both File\(s\)**, and an option to create a version of the existing working copy.

    ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

    If you choose the **Overwrite Existing File\(s\)** option, then the file that is being uploaded replaces the current working version of the existing file at the original location. The UUID is not created or changed.

    If you choose the **Keep Both File\(s\)** option, a new copy of the file is created with a suffix \(like filename0.extension\). A new UUID is also assigned to the newly copied file.

    With Overwrite existing file\(s\) option, if you choose the option to create a version from the existing working copy, then a new version from the working copy of the document is also created.

    >[!NOTE]
    >
    > **Create new Version for Uploaded File** feature must be enabled by your administrator. If this feature is enabled, a new version for the uploaded file is created. If the option is deselected, then a version of the uploaded file is not created. For more details, see *Create New Version for Uploaded File* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

    If a file is already checked out for edits by another user, and you attempt to upload and overwrite the existing file, then it fails and displays an error.

    >[!NOTE]
    >
    >The **Overwrite Checked out File on Upload** feature must be disabled by your administrator. If this feature is enabled, you can overwrite checked-out files. If the feature is not enabled, then a checked out file is prevented from being overwritten. For more details, see *Overwrite Checked out File on Upload* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.


-   *Drag-and-drop files at different location*: A new copy of the file is created and a new UUID is also assigned to it at the new location. Here, the file name is same as the original file name.


**Drag-and-drop with filenames based on a UUID pattern**

*Drag-and-drop file at the same location*: You are given the options to **Overwrite Existing File\(s\)** along with the option to create a version of the existing working copy.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

When the file is overwritten, there is no change in the file name or its UUID.

If you select the **Create Version for the Existing Working Copy** option, then a new version from the working copy of the document is created; the new file is uploaded, a new version of the file is also created, and it is made as the working copy of the document.

**Create new Version for Uploaded File** feature must be enabled by your administrator. If this feature is enabled, a new version for the uploaded file is created. If the option is deselected, then a version of the uploaded file is not created. For more details, see *Create New Version for Uploaded file* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.


*Drag-and-drop file at different location*: You are given the options to **Overwrite Existing File\(s\)**, **Move File\(s\) to New Location**, and an option to create a version of the existing working copy.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

If you choose the **Overwrite Existing File\(s\)** option, then the file that is being uploaded replaces the existing file at the original location. The UUID is not created or changed.

If you choose the **Move File\(s\) to New Location** option, then the existing file is moved to the current location and then it is overwritten with the file being uploaded. Moving a file to the new location does not break any existing references from or to the file.

With replace or moving the files, if you choose the option to create a version from the existing copy, then a new version from the working copy of the document is created; the new file is either replaced at the existing location or moved to the new location.


## Move files in bulk {#move-files-bulk}

AEM Guides comes with the Bulk Move Tool that helps an administrator to move a folder having large number of files from one location to another. This tool can easily move files within one or more folders into a different folder in your AEM repository. One of the major features of this tool is that it not only moves a large number of files, but it also maintains the references to and from the files being moved. You can tweak the number of files that you can move in batches without hampering the authoring and publishing tasks.

>[!NOTE]
>
> The Bulk Move Tool works only at folder-level. If you want to move individual topic or map files, then use the regular move tool from AEM's Assets UI.

Here are some of the features provided by the Bulk Move Tool:

-   You can tweak the number of files to process in each batch. This might require you to run a few tests before arriving at an optimal number that your system can easily handle.
-   Authoring and publishing services run smoothly without any interruption from the move operation.
-   Have compete control over the time interval in-between subsequent \(running of\) batch processes. This time interval ensures that the post-processing operation is completed before starting the next batch of files.

-   Auto-handling of folders with same name. This feature ensures that even if there are folders with same name being move, they are not overwritten.

-   Auto-handling of references to and from the files being moved.


You must consider the following points before running the batch process:

-   If you plan to move topics that are currently under review, you must close the review process on all such topics before moving them. Not closing the review task will break the review process.
-   You must run only a single bulk move operation on the system at any time. This ensures proper handling of references to and from the topics being moved.


To move files in bulk, perform the following steps:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools.
1.  Click on the **Bulk Move Tool** tile. 
1. The Bulk Move Tool page is displayed based on your setup. Provide the following details on the **Bulk Move Tool** page:

    <details>
        
    <summary> Cloud Services and On-premise UUID-based file system </summary>

    ![](images/bulk-move-tool-uuid.png){width="650" align="center"}

    >[!TIP]
    >
    > Select <img src="images/info-icon.svg" width="25">   near any field  to view more details about it. 
    

    -   **Add suffix to duplicate folders**: In case you are moving folders that have same name, then you must select this option. For example, in the previous screenshot, the **Source path** contains the name of folders to move. The folder named topic exists at two different locations — test-A and test-B. When you select this option, then the folders will move successfully. The first moved folder will be named topic whereas the second folder will be named topic0. The move operation adds a suffix in sequential series \(0, 1, 2, and so on\) to the folders with the same name.

        If you are moving folders with the same name without selecting this option, then the operation will abort with a message.

    -   **Source path\(s\)**: Specify the location of folders that you want to move. 
       
         - Select  **Browse Folder**  <img src="images/browse-folder-icon.svg" width="25">    to open the browse file dialog. Select the folders you want to move and click **Select** to complete the process. 

        - You can also type or copy and paste the source location. Press Enter to add the folder to the list. 

            The selected folders are listed along with their path. Hover over the folder tag to view the complete path.
        - You can also remove any folder by clicking **Remove** <img src="images/remove-folder.svg" width="25"> near the folder.


    -   **Destination path**: Specify the location where you want to move the source folders.

        - Select  **Browse Folder** <img src="images/browse-folder-icon.svg" width="25"> to open the browse file dialog. Select the location where you want to move the source folders. and click Select to complete the process.
        - You can also type or copy and paste the destination path. 

        The selected folder is displayed along with its path in the text box. 


    -   Click **Bulk move**.

        The system starts moving files from the source to destination location. Once the process completes, a summary of the move process is shown at the right of the page.

        ![](images/bulk-move-summary-uuid.png){width="650" align="center"}

    </details>

    <details>
        
    <summary> On-premise non-UUID-based file system </summary>

    ![](images/bulk-move-tool-non-uuid.png){width="650" align="center"}

    >[!TIP]
    >
    > Select <img src="images/info-icon.svg" width="25">   near any field  to view more details about it. 

    - **Batch size**: Specify the number of files to move in a single batch. The default values if 50 files.
    - **Sleep interval**: Specify the time in seconds that the process will wait before starting the next batch. During this sleep time interval, the system fixes the references to and from the moved files. The default sleep interval is 60 seconds.


    -   **Add suffix to duplicate folders**: In case you are moving folders that have same name, then you must select this option. For example, in the previous screenshot, the **Source Path** contains the name of folders to move. The folder named topic exists at two different locations — test-A and test-B. When you select this option, then the folders will move successfully. The first moved folder will be named topic whereas the second folder will be named topic0. The move operation adds a suffix in sequential series \(0, 1, 2, and so on\) to the folders with the same name.

        If you are moving folders with the same name without selecting this option, then the operation will abort with a message.

    -  **Update references of checked out files**: If you are moving folders containing checked out files, then it is recommended to select this option. If you select this option, then all files that are checked out will be saved and checked in with a new revision. This new revision is then moved to the destination location.  

        If you do not select this option, then the checked out files are moved to the destination folder in the same checked out status. However, there could be some loss of data in this moving process.
    

     -   **Source path\(s\)**: Specify the location of folders that you want to move. 
        
            - Select  **Browse Folder**  <img src="images/browse-folder-icon.svg" width="25">    to open the browse file dialog. Select the folders you want to move and click **Select** to complete the process. 

            - You can also type or copy and paste the source location. Press Enter to add the folder to the list. 

                The selected folders are listed along with their path. Hover over the folder tag to view the complete path.
            - You can also remove any folder by clicking **Remove** <img src="images/remove-folder.svg" width="25"> near the folder.


    -   **Destination path**: Specify the location where you want to move the source folders.

        - Select  **Browse Folder** <img src="images/browse-folder-icon.svg" width="25"> to open the browse file dialog. Select the location where you want to move the source folders. and click Select to complete the process.
        - You can also type or copy and paste the destination path. 

             The selected folder is displayed along with its path in the text box. 
             
    -   Click **Bulk move**.     

         The system starts moving files from the source to destination location. Once the process completes, a summary of the move process is shown at the right of the page.
        ![](images/bulk-move-summary-non-uuid.png){width="650" align="center"}
 </details>

## Search DITA content 

By default, AEM does not recognize DITA content, thus, it doesn't provide any mechanism to search DITA content within its repository. AEM Guides adds a layer on top of AEM, which enables AEM to understand and process DITA content. The Search DITA content feature in AEM Guides allows you to search for DITA content within AEM repository.

>[!NOTE]
>
>Your system administrator can configure the **DITA Element** search component and then you can use the feature from the AEM Assets UI. For more details see, *Add DITA Element search component in Assets UI* section in Install and configure Adobe Experience Manager Guides as a Cloud Service.

Using the search feature, you can:

-   Search for DITA content based on an element value; for example, `author`= xml
-   Search for DITA content based on an attribute value; for example, `@platform`= windows
-   Use a combination of DITA element and attribute value; for example, `author`= xml `AND` `@platform`= windows

Perform the following steps to search for DITA content within AEM repository:

1.  Open the Assets UI.

1.  In the left rail, select **Filters**.

    ![](images/left-rail-filter.png){width="450" align="center"}

    The content filtering options are shown in the left rail. You will also find the filtering option—DITA Element, which is used to filter DITA content.

    ![](images/dita-element-search.png){width="450" align="center"}

1.  *\(Optional\)* In the **Select Search Directory** field, browse for the location that you want to search in.

1.  In the **DITA Element** filter, provide the **Element Name**, **Attribute**, and a value that you want to search for. For example, to search for documents that have `author` element that is of `@type` creator you need to provide the information as shown in the following screenshot:

    ![](images/search-params.png){width="650" align="center"}

    The search criteria entered in the **DITA Element** filter is shown at the top of the search bar. The files matching the search criteria are shown in the **Search Results** area.

    Consider the following points while specifying the search criteria:

    -   To search for an exact phrase, enter the phrase in the Value field within quotes `"`phrase search`"`.
    -   You can add up to 3 DITA element search criteria.
    -   In case you specify multiple search criteria, then all of them will be combined using the AND logic.
    -   You cannot use wildcard character in your search criteria. For example, to search for platform \(attribute\) with value of Windows—you cannot specify \*form or Windo?s.

**Checkout status filter in search**

In addition to the DITA Element filter, AEM Guides also lets you to search for content based on their checkout status. This is helpful when you want to quickly filter out files that are currently checked out by you and want to check them back in.

Perform the following steps to search for files based on their checkout status:

1.  Open the Assets UI.

1.  Click **Filter** in the left rail.
1.  Enter your search keyword in the Search bar.
1.  Apply the required filters from the left rail.

    For example, you can apply **Checkout Status** filter to show the checked out or checked in topics. You can further refine this list by choosing the user or group from the Checked Out By list.

    Your search result is displayed.


## Delete files 

Deleting files from AEM repository is a restricted feature, which is controlled by your system administrator. Based on the configurations, deleting files could be restricted if they are:

-   Checked-out
-   Have incoming or outgoing references

You could also delete files only if you belong to a specific user group that has privileges to delete files.

>[!NOTE]
>
> For more details on the configurations on file management, see *Prevent deletion of checked out files* and *Prevent deletion of referenced files* sections in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

If your administrator has given the file delete permission to all user, then the following message is displayed when you delete files containing references:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

In this scenario, you can forcefully delete files without removing the incoming or outgoing references from the files.

If the delete permissions are given to a specific user group, then also the above message will appear for users belonging to that group. However, for other users, the following message is displayed:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

In this scenario, users won't be allowed to delete files until all incoming and outgoing references have been removed.

## Work with media files 

Media files like images and videos are an integral part of your content. While you upload and manage your content, you might also work with media files.

If your media file has undergone any changes, you can find and preview the files in the **Version History**.To find out changes in the different versions of a media file:

1.  Access the file in **Assets UI**.
1.  Select the file for which you want to view the version history.
1.  In the left rail, click **Version History** and select a version.
1.  You can also see the thumbnails of the different versions under Version History.

    ![](images/media-version-history-icon.png){width="800" align="center"}

1.  From the listed versions, select the one that you want to use as the base version and click **Preview Version**. The preview of the selected version is shown in the Version Preview window.

    ![](images/media-version-preview.png){width="650" align="center"}


**Parent topic:**[Manage content](authoring.md)
