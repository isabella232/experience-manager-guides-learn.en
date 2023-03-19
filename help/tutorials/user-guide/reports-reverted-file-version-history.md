# Reverted files version history report {#id205BBC00PRK}

When you are working on multiple simultaneous releases along with multiple authors, your content is bound to have multiple versions. There could be some common information across multiple releases, which different authors could use in their project. To handle such work assignments, authors could end up with multiple versions of files. Such versions could simply be a newer version of a file or a revert to an earlier version. It is a complex task to identify when a file was reverted and why.

AEM Guides allows you to generate a version history report for an individual file or for all files in a folder. This version history gives you a consolidate view of all versions of a file that were reverted and who created those versions and the reason for creating those versions.

You can access this report from the following places:

-   **Assets UI**: by selecting a file and opening the **Version History** from the left rail. The **Version History** view contains the **Revert Version Logs** link at the bottom of the panel. When you click on this link, the selected file's history of the reverted versions is displayed.

    ![](images/revert-log-from-assets-ui.png)

-   **Topic preview**: when you are previewing a topic, there also you can bring up the **Version History** panel from the left rail. You will get a panel similar to the Assets UI from where you can click the **Revert Version Logs** link to access the reverted version history of the active document.

-   **AEM's Tools section**: you can also access this report from AEM's Tools section. The following procedure explains how you can access the revert version history from the AEM's Tools section.


Perform the following steps to access the Revert History report:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Click on the **Version Revert History** tile.

    A blank Revert Version History page is displayed wherein you need to browse to and select a file or folder to generate the report.

1.  Click **Show Logs** to generate the report for the selected file or folder.

    ![](images/revert-version-history-report.png)

    The report contains the following details:

    File Name
    :   The title of the topic. Clicking on the topic’s title link opens the topic preview.

    Time Stamp
    :   The date and time when the topic was reverted to an earlier version.

    User
    :   Name of the user who reverted to an earlier version.

    Revert From
    :   The original version number of the file from where it was reverted.

    Revert To
    :   The version to which the file was reverted to.

    Comment
    :   Any comment given by the user who reverted the file.


**Parent topic:**[Reports](reports-intro.md)

