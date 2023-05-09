---
title: Version management
description: Learn how  Version management works
---

# Version management {#id181GB000XY4}

Versioning is an important aspect of any content management system. It allows you to create a snapshot of your digital asset at a specific point in time. With a version of a digital asset in place, you can restore the required version of the asset and update it. Typically, for creating a version of any asset, you would check out and check in the required asset.

As an administrator, you can enforce rules that will restrict users from editing a file without checking it out. Similarly, you can ensure that all checked out files are checked in back to avoid any data loss.

In a multi-use environment, it is also important to ensure that users do not delete files from the system. This requirement is more critical for files that are checked out by other users.You can allow or prevent the users from overwriting files checked out by another users. To prevent users from accidentally deleting checked out files from the system, AEM Guides provides a configuration that you can use. In addition to checked out files, you can also control deletion of files that contain references or are referenced from other files. Besides, you can also create new version for uploaded file.

## Create new version for uploaded file 

>[!NOTE]
>
> This configuration is applicable only while uploading files.

To create a new version of the uploaded file, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Create New Version for Uploaded File** option.

    By default, this option is turned OFF.

    When the option is selected then a new version management mechanism takes place and overridesthe default upload behavior that is for any subsequent upload it will save the contents of the uploaded file as a new version. If the option is deselected then AEM Guides uses the AEM's default version management mechanism.

1.  Click **Save**.


>[!NOTE]
>
> You can upload files in batches of 70 or less, if you enable the property **Create New Version for Uploaded File** \(create.ver.new.content\) and use the **Assets UI**to bulk upload assets.

## Configure settings to allow editing of checked out files 

The AEM Guides' Web Editor allows you to create and update DITA topics. You can configure the Web Editor to allow editing of only those documents that have been checked out from the repository. This ensures that no other writer accidentally overwrites a topic that is opened for editing by another writer. Once a topic is opened for editing, an author can check-in the file at the time of closing the file.

Another important rule is to ensure that files that have been checked out are checked back into the system. This prevents users from accidentally closing the files without checking them back in.

Perform the following steps to enable these features:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Disable Edit Without Checkout** option.

    ![](assets/xml-editor-config.png)

    With this option, users will not see the Edit option in the toolbar until they check out a file.

1.  Select the **Ask for Check-in on Close** option to show a warning message whenever a checked out file is closed without saving or checking it back into the repository.

1.  Click **Save**.


>[!NOTE]
>
> Irrespective of whether you turn on or off this feature, the file Check Out and Check In options are always available in a topic preview.

## Overwrite checked out file on upload 

>[!NOTE]
>
> This configuration is applicable only when you create files from the Assets UI and not when you upload files using the WebDAV tool.

To allow users to overwrite the file on upload that has been checked out by them or some other user, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Overwrite Checked out File on Upload** option.

    By default, this option is turned ON. With this option selected, users will be able to overwrite checked out files. If the option is not selected, then the file is prevented from being overwritten if it is checked out by them or some other user.

1.  Click **Save**.


## Prevent deletion of checked out files 

To prevent users from accidentally deleting files that have been checked out by them or some other user, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Prevent Deletion of Checked Out Content** option.

    By default, this option is turned ON. With this option selected, users will not be able to delete checked out files.

1.  Click **Save**.


To support this feature, a new index property `drivelock` is added in `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png)

In addition to the new index property, ensure that the following properties are set on `/oak:index/damAssetLucene`:

-   `jcr:primaryType`=`"oak:QueryIndexDefinition"`
-   `async`=`"async"`
-   `compatVersion`=`"{Long}2"`
-   `evaluatePathRestrictions`=`"{Boolean}true"`
-   `reindex`=`"{Boolean}false"`
-   `reindexCount`=`"{Long}3"` *\(this is the count of how many times re-indexing is done, it is replaced with the installation of our package\)*
-   `type`=`"lucene"`

>[!NOTE]
>
> You can change the value of `reindex` to `"{Boolean}true"`. This will enable faster search results for the checked-out files inside a hierarchy of folders.

## Prevent deletion of referenced files 

As an administrator, you can control who can delete files from the AEM repository. Specifically, if a file contain references or is referenced by some other file, then you can define who can delete such files.

Using this configuration, you can allow or disallow all users from deleting files, or allow only a specific user group to delete files. If file deletion is allowed, then the following process is followed:

-   If you are deleting a folder, which contains all referenced and referencing files, then all files are deleted. The process will first delete all files that do not contain any references, followed by the files that contain references or are referenced.

-   If you are deleting a folder, and any file within the folder is referenced by a file outside that folder, then you will be prompted to remove the reference before deleting the file.


To define who can delete a file that contains references or is referenced by other files, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Locate the **Block Deletion for Referenced Assets** option.

1.  Depending on who you want to give access for deletion, specify one of the following constants:

    -   allow\_unsafe\_delete\_for\_all: Give permission to all users to delete files. In this case, if the file\(s\) contain references or is referenced by other files, then also you can forcefully delete such file\(s\). Before deleting the file, you will be shown a prompt with the references, you can cancel the delete operation, remove the references, and then finally delete the file\(s\). Or, you can forcefully delete the file\(s\) without removing the references.

        ![](assets/allow_unsafe_delete-force-delete.PNG)

    -   allow\_unsafe\_delete\_for\_delete\_assets\_group: An Administrator or a user belonging to the *delete-assets* group is allowed to delete files. If any other user tries to delete files with any references, then they will not be allowed to delete such files until all references are removed. The following screenshot appears when a user, who does not have permissions, tries to delete files.

        ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG)

    -   block\_unsafe\_delete\_for\_all: Disallow all users \(including Administrators\) from deleting files until the references to and from the file\(s\) are removed.

1.  Click **Save**.


## Purge older versions of DITA files 

When you update content and create new versions, the previous versions of DITA files are maintained in the repository. Many versions might get created for your DITA files over a period and can collectively take up a large amount of space in your repository. AEM Guides allows you to configure the older versions which should be deleted from the repository.

You can access this utility using the given URL if you have administrative rights:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

The version of a DITA file that meets any of the given criteria is maintained and not purged:

-   Is the first version of a file
-   Is included in a baseline
-   Is included in any translation or review workflow
-   Has a label applied to it
-   Meets the defined age or number of version criteria

Perform the following steps to purge the older versions:

1.  Enter the following details about the files you want to purge:

    ![](assets/preview-purge-report.png)

1.  -   **Number of Versions to Retain from the Latest Version**: Enter the number of versions that should be retained and not purged. For example, if we enter 5 then the last 5 versions are retained, and the versions prior to that are qualified to be purged in case other purging conditions are met.
-   **Retain Versions Created Within Timespan \(In Days\)**: Enter the maximum age of a version in days. The versions older than the given number of days are qualified to be purged in case other purging conditions are met. For example, if we enter 100, all versions created before 100 days are qualified to be purged in case other purging conditions are met.
-   **Path**: Select the path of the file or folder whose files you want to purge.

    >[!NOTE]
    >
    > You can only purge DITA files.

1.  Click **Preview Purge Report**.

    >[!NOTE]
    >
    > There can be only one purge task at a time. You cannot initiate another version purge operation if one is under process.

    The version purge report is generated.

1.  Download version purge report and check the files and versions that will be purged.
1.  You can choose to **Cancel Purge** or **Start Purge**.

    ![](assets/download-purge-report.png)

    The purging status is displayed.

    Click **Download Version Purge Report** to view the purged versions. This report provides the purging status on all versions along with reasons why a particular version was retained or why it got purged.


>[!NOTE]
>
> The report is downloaded at the following location:

/var/dxml/versionpurge

