# Preview a topic {#id1696II000QR}

Once a topic is created, AEM Guides generates a preview of the topic. The Preview mode provides various features that you can use to work with your document.

Perform the following steps to preview a topic:

1.  In the Assets UI, navigate to the topic that you want to view.

1.  Click on the topic you want to view.

    A preview of the topic is displayed in the Assets UI.

    >[!NOTE]
>
> You can see the version of the active topic or DITA map in the top right corner of the topic's file tab.


>[!IMPORTANT]
>
> The positioning of the following features in the Preview toolbar could differ based on your AEM server's setup. Some of the features might be available in the main toolbar, while other could be available under the More menu.

**Features available in preview mode![](images/preview-screen.png)

**
:   **You can perform the following operations from the toolbar in the preview mode:**

Properties
:   View the properties of the selected topic. Based on your AEM version, you could see properties like metadata, schedule \(de\)activation, references, document state and more.

    >[!NOTE]
>
> A topic's title property is auto-populated from the `title` tag of the DITA topic or map. If you make any change in the title using the properties window that change is lost. If you want to update the title property, you should do it using the Web editor.

    The Properties page contains useful information about the references, such as where a map or topic is being used, or what references are contained in a document. The Properties page lists two types of references for a document - **Used In** and **Outgoing References**.

    The **Used In** references list the documents where the current file is being referred or used. The **Outgoing References** lists the documents that are referred in current document.

    The \(+\) icon in the **Used In** references section allows you to further navigate upwards to find where that topic is being used or referred.

    ![](images/used-in-dialog_cs.png)

    Clicking the ![](images/right-arrow-used-in-dialog.svg)icon next to a document shows the map or topic files where that document is being further referred.

Conditional Filtering \(A/B\)
:   **** If your topic has conditional content, then you will see the A/B icon on the toolbar. Clicking on this icon opens a pop-up that allows you to filter the content as per the available conditions in the topic.

    >[!NOTE]
>
> The conditional content is highlighted using light background color in the Web Editor.

    ![](images/conditional-popup_cs.png)

Edit
:   Open the topic for editing in the Web Editor. The **Edit** option will not be available if your administrator has enabled the **Disable Edit Without Checkout** option. With the option enabled, you will see the **Edit** option only after checking out a topic file.

Key Resolution
:   ****If you want to use a keyspace file for the topic, click the Key Resolution icon. You can then choose a key space from the Key Resolution pop-up.

Source
:   Open the XML source code of a file. You can view the underlying XML code of a map, topic or DITAVAL file by opening the file in the Preview mode and clicking the Source icon. The XML Source pop-up displays the XML source code. You can select a specific code from the file or press `Ctrl`+`a` to select the entire content.

    >[!NOTE]
>
> To get the source code view of a DITA map file, select the file in Assets UI and click Source.

    ![](images/xml-source-code-view-from-preview_cs.png)

Share UUID Link
:   AEM Guides allows you to share the UUID-based links for DITA maps, topics, and image files from the following places:

    -   Assets UI
    -   DITA map's console
    -   Topic or image's Preview

    A new option **Share UUID Link** is shown in the toolbar of the above-mentioned areas. The following screenshot shows the **Share UUID Link** option in the Preview mode of a topic:

    ![](images/share-uuid-link_cs.png)

    In the Asset UI, this option is visible when you select a file. While in the Preview mode, this option is available in the main toolbar by default. In a DITA map console, this option is visible in the Output Presets section.

    Once you have copied the URL, the same can be shared with other users to give them direct access to the file. This link remains valid even when the file is moved to some other location in the repository. The only time the link will fail is when the file is deleted from the repository.

    If you share the link from DITA map console or a file's preview mode, then the user taken to same view of file. However, when you share a map file's link from the Assets UI, then the user is taken to the map's console. Similarly, for a topic or image file, the file's preview is shown.

    >[!IMPORTANT]
>
> The link cannot be used as a reference link in other topic, it only gives direct access to the file in the repository. Also, the link remains valid as long as the file is available in the repository. Even if the file is moved to some other location in the repository, the link remain valid. The link will fail only when the file is deleted from the repository.

Check Out/Check In
:   Toggles the Check Out and Check In features. When a file is checked out, the current user gets an exclusive write permission on the file. A checked out file can be opened in the Web Editor for editing. Once you have made the required changes, click the Check In icon to save the file in DAM.

    When you check out a topic, the status of the file is shown as checked out in the card view and in the list view.

    Checked out file in the card view:

    ![](images/checkout-card-62.png)

    Checked out file in the list view:

    ![](images/checkout-list-62.png)

    If the Checked Out column is not visible, select **View Settings** under **List View** and select the **Checked Out** status in the **Configure Columns** dialog.

    ![](images/list-view-settings-check-out_cs.png)

    >[!TIP]
>
> See the Versioning of content section in the Best practices guide for best practices around working with file check-out and check-in.

Web-based version difference
:   If your topic has undergone some changes, you can easily find out the changes made in different versions of that topic. To find out changes in different versions of a topic:

    >[!IMPORTANT]
>
> The method described in the following procedure is only applicable for DITA files. For non-DITA files, use the Timeline view to create versions or restore an existing version of a file.

    1.  Open the topic in Preview mode.

    2.  In the left rail, click **Version History** and select a version.

        ![](images/timeline-versions62_cs.png)

    3.  From the listed versions, select the one that you want to use as the base version and click **Preview Version**. The preview of the selected version is shown in the Version Preview window.

    4.  From the **Show Diff** list, select the version with which you want to compare the base version.

        ![](images/show-diff-list-cropped.png)

        The changed content is highlighted in the topic preview. Content highlighted in green signifies the newly added content and content in red is the deleted content.

        ![](images/version-difference.png)


Branch, revert, and subsequent versioning
:   In a typical authoring environment, you would need to create a new branch of a topic to cater to a specific release. Just like any other version management system, AEM Guides allows you to create a branch from an existing version of a topic, or revert to an older version of a topic. Using the version management features offered by AEM Guides, you can perform the following tasks:

    -   Create a branch from an existing version of a topic
    -   Create subsequent versions in a new branch
    -   Revert to a specific version of a topic

    The following illustration shows the typical branching and subsequent versioning system:

    ![](images/branching_illustration.png)

    For any new topic, the first version is numbered as 1.0. Thereafter, every new version of the topic is saved with an incremental number such as 1.1, 1.2, and so on. Once you create a branch of a topic, a new branch is created taking the version number from where the branch is created and adding a .0 at the end of the version. As seen in the illustration, a new branch is created from version 1.1 of a topic. The new branch is versioned as 1.1.0. Thereafter, every time you save a new version of the topic in this branch, it gets an incremental version number such as 1.1.1, 1.1.2, and so on.

    Similar to branching, you can also revert your working or current version to any version that exists in the repository. To revert to a version, simply select the desired version of the topic and click **Revert to This Version** in the **Version History** panel.

    Perform the following steps to create a branch, revert to a version, and maintain subsequent versions of a topic:

    >[!IMPORTANT]
>
> The method described in the following procedure is only applicable for DITA files. For non-DITA files, use the Timeline view to create versions or restore an existing version of a file.

    1.  Access the topic in Assets UI.

        >[!NOTE]
>
> You can also open the topic in Preview mode and proceed with Step 3.

    2.  Select the topic for which you want to create a branch.

    3.  In the left rail, click **Version History**.

        >[!NOTE]
>
> A list of versions available for the selected topic is displayed. Each version contains the timestamp, user name, version comment, and [label](web-editor-use-label.md#) information.

    4.  Select a version from where you want to create a branch. In the following screenshot, version 1.2 is selected for creating a branch.

        ![](images/branching.png)

        >[!NOTE]
>
> The current version of a topic contains *\(Current\)* mentioned next to the version number.

    5.  Click **Revert to This Version**.

        A message appears asking you to confirm the creation of a new branch.

    6.  *\(Optional\)* In the message prompt, you get an option to select the **Save The Current Working Copy As A New Version**. The following two actions are possible based on the selection of this option:

        -   If you select this option, then a branch is created from version 1.2. And, a new version of the topic is also created from the current working copy of the topic and saved as the next version – 1.4.

            ![](images/next_version_created_over_working_copy.png)

            Version 1.2 becomes your current working copy of the topic. Any version saved after this is created under the new branch of 1.2. For example, the subsequent version of a new topic in this branch will be saved as 1.2.0.

            ![](images/new_version_in_branch.png)

        -   If you do not select this option, then no new version from the current working copy of the topic is created. A new branch is created from version 1.2 of the topic. Any subsequent version of the topic is saved under the 1.2 branch as 1.2.0, 1.2.1, and so on.

            ![](images/new_version_without_working_copy.png)

    7.  Click **OK**.


    A new branch is created from the selected version of the topic. The above process is also applicable for reverting to a specific version of a topic. Reverting to a specific version technically means that you create a new branch from the selected version and make that version the current working copy of the topic. You can also view the history of files that have been reverted in the Version Revert History report. For more details about this report, see [Reverted files version history report](reports-reverted-file-version-history.md#).

**Parent topic:**[Create and preview topics](create-preview-topics.md)

