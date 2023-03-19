# Work with the Advanced Map Editor {#id1942D0S0IHS}

The Advanced Map Editor comes with intuitive user interface and it is similar to the Web Editor. When you open a map file in the Web Editor, you get an option to edit the map file using the Advanced Map Editor interface. The Advanced Map Editor allows you to add topic references, key references, structure your content and more.

In addition to editing map files directly from the Web Editor, you can also open topic files in a map for editing the Web Editor. This topic walks you through the features in the Advanced Map Editor and how you can open and edit files in a DITA map in the Web Editor.

## Add topics to a map file 

Perform the following steps to build your map file using the Advanced Map Editor:

1.  In the Assets UI, navigate to the map file that you want to edit.

    >[!NOTE]
    >
    > Ensure that you have not enabled the asset Select mode.

1.  To get an exclusive lock on the map file, select the map file and click **Check Out**.

    >[!NOTE]
    >
    > Once you have an exclusive lock on a map file, other users would not be able to edit the map. However, they would be able to work on the topics within the map file. If your administrator has configured your Web Editor to checkout files before editing, then you will not be able to edit a file until you check it out. Similarly, if configured, you will be asked to check-in any checked-out a file before closing it

1.  With the map file selected, click **Edit Topics**.

    ![](images/edit-map-main-menu.png)

    Or, you can also select the **Edit Topics** option from the action menu on the map file:

    ![](images/edit-map-action-menu.png)

    The map file is opened for editing in the in the Web Editor.

1.  Click the **Edit** icon.

    ![](images/edit-map-icon.png)

    The map is opened in the Advanced Map Editor interface. If you have opened a new map file, then only the title of the map is shown in the editor.

    ![](images/new-map-file-in-editor.png)

    -   **A** - \(*Main toolbar*\): This is similar to the Web Editor's main toolbar. See [Main toolbar](web-editor-features.md#id2051EA0G05Z) in the Web Editor for more details.

    -   **B** - \(*Secondary toolbar*\) This is the Secondary toolbar that allows you to work with map files. For more information about the functionalities available through Secondary toolbar, see [Features available in the Advanced Map Editor's toolbar](#id205DEC0005Z).
    -   **C** - \(*Map views*\): Allows you to switch the Map Editor between the Layout, Author, Source and Preview. The **Layout**view allows you to organize the topics in a DITA map. This gives the tree or hierarchical view of the map. The **Author** view allows you to edit the topics in the Map Editor. This also gives the WYSIWYG view of the map file. The **Source** view allows you to work with the underlying XML of the map file. The Preview gives you a consolidated view of all topic and sub-maps within the map file. The **Close** link closes the map file.

    -   **D** - \(*Left Panel*\): Gives access to the left panel which gives you access to the Favorites, Repository, Map, Outline and other features. You can expand or collapse it by clicking the Expand Sidebar icon \(![](images/sidebar-expand-icon.svg)\). For more details about the features available in the left panel, see [Left panel](web-editor-features.md#id2051EA0M0HS) in the Web Editor.

    -   **E** - \(*Middle Area*\): Map content editing area.

    -   **F** - \(*Right Panel*\): Gives access to the Properties panel. You can see the content properties and the map properties of the selected topic or map. For more details about the functionalities available in this panel, see [Right panel](web-editor-features.md#id2051EB003YK) in the Web Editor.

1.  In the Left Panel, switch to the **Repository View**.

1.  In the AEM repository, navigate to the folder that contains the topics or sub-maps that you want to add.

1.  Select the topic or map file in the **Repository View** and drag-and-drop it into the \(middle\) map content editing area.

    The topic is added in the map.

    ![](images/map-editor-add-topic.png)

1.  To add subsequent topics or a sub-map, drag-and-drop the topic or sub-map to the required location in the map.

    Consider the following points while building your map file:

    -   The file is added at a location where the horizontal bar appears in the map editing area. In the following screenshot, the *Overview* topic will get added in between the *General Description* and *Launch and Landing Site* topics.

        ![](images/horizontal-line-in-adv-map-editor.png)

    -   To replace a topic, place the topic on top, left, or right of the topic that you want to replace. A Vertical bar to the left or right of a topic indicates that it will get replaced with the topic being dropped on it.

        ![](images/vertical-bar-left-right.png)

        However, before replacing a topic, you get a confirmation prompt. The topic is replaced only after you give the confirmation.

        ![](images/replace-topic-confirm.png)

    -   If you add a sub-map to your DITA map, the sub-map is shown as a link in the DITA map. To view all the topics of the sub-map, Crtl+Click the sub-map link. The content of the sub-map are shown in a new tab. Similarly, to open a topic from the DITA map, Crtl+Click the topic link and it opens up in the new tab.

    -   You can use shortcut keys CTRL+Z and CTRL+Y or their respective icons in the toolbar to undo or redo any change in the map.

    -   To change the position of a topic, select the topic \(by clicking on the topic icon\), then drag-and-drop it at the desired location in the map file. Ensure that the horizontal bar is visible at the location where you want to place the topic. In the following screenshot, the topic *Launch and Landing Site* is being moved after the *Overview* topic.

        ![](images/move-topic-adv-map-editor.png)

    -   To check the properties of your map file, right-click anywhere in the map editing area and choose **Properties** from the context menu. Based on your AEM version, you could see properties like metadata, schedule \(de\)activation, references, document state and more.

1.  Click **Save**.


## Features available in the Advanced Map Editor's toolbar {#id205DEC0005Z}

The toolbar in the Advanced Map Editor is similar to the topic Web Editor. The basic operations like toggling the left panel, saving map, creating a new version of map, undo/redo last operation, and delete the selected elements are common in both editors. For detail about how these operations work, see [Know the Web Editor features](web-editor-features.md#) section.

The following map-specific operations are also available on the toolbar in the Layout and Author views:

## Layout view {#id205DEC0005Z}

When you open a map for editing it opens the Layout view of the Map Editor.The Layout view displays the map hierarchy in a tree view and allows you to organize the topics in a map.

>[!NOTE]
>
> The Layout view only displays the references present in a map. If any references are broken, then a small cross symbol is displayed on the left of the reference

You can perform the following tasks in the Layout view:

Insert Topic Reference – ![](images/insert-topic-reference.svg)
:   Displays the topic search dialog. Navigate to the topic/map file that you want to insert and click Select to add it to the map.

    ![](images/insert-topic-reference-dialog.png)

Insert Topic Group – ![](images/insert-topic-group.svg)
:   Insert the `topicgroup` element. For more information about grouping topics, see the [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentation in OASIS DITA Language Specification.

Insert Key Definition – ![](images/Key_icon.svg)
:   Displays the Insert Keydef dialog. Use this dialog to define any key definition that you want to use in the map.

    ![](images/insert-key-definition-dialog.png)

Insert Before/Insert After – ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)
:   Displays the Insert Element dialog. Select the element that you want to insert in the map. Depending on the operation, the new element is inserted before or after the current element in the map.

Insert Front Matter - ![](images/frontmatter.svg)
:   This icon is displayed when you open a bookmap for editing. You can insert components in the beginning of the book like a Table of contents, an Index, and a List of Tables.

Insert Back Matter -![](images/backmatter.svg)
:   This icon is displayed when you open a bookmap for editing. You can insert components for a end of the book like an Index, a Glossary, and a List of Figures.

Move the Selected Item Left/Right – ![](images/left-arrow-icon.svg) / ![](images/right-arrow-icon.svg)
:   Click the left arrow to move the topic towards left side in the hierarchy. This essentially promotes the respective topic one level up in the hierarchy. For example, clicking the left arrow while a child topic is selected make it the sibling of the topic above it. Similarly, if you click the right arrow, the topic is pushed towards the right side making it the child of the topic above it.

Move the Selected Item Up/Down ![](images/arrowup.svg)– / ![](images/arrowdown.svg)
:   Click the up or down arrow icons' to move the topic up or down in the hierarchy.

    >[!NOTE]
    >
    > You can also drag-and-drop the references to move them in a map.

Lock/Unlock – ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)
:   Gets a lock on the map file and release the lock. If you have unsaved changes in your map file, then at the time of releasing the lock, you are prompted to save the map file. The changes are saved in the current version of the map file.

Merge – ![](images/merge-icon.svg)
:   For more details about merging content from a different version of the same or a different file, see [Merge](web-editor-features.md#id205DF04E0HS) in the Web Editor.

Version History— ![](images/version-history-web-editor-ico.svg)
:   Check the available versions and labels on your active topic, and revert to any version from theeditor itself.

Version Label— ![](images/version-label-icon.svg)
:   Displays the version label management dialog. Select a version from the dropdown list. Choose the label you want to apply to the selected version and click **Add Label** to add it.

View Options—![](images/view-options.svg)
:   Displays a dropdown which gives you the option to Show Line Numbers, Show Check box, and Show FileName.

    -   **Show Line Numbers**

        Shows or hides the line number for each topic. The line numbers are shown depending on the level in the hierarchy.

    -   **Show Check Box**

        Shows or hides a checkbox for each topic. You can use the checkbox to select the topic\(s\) and perform various tasks using the Options menu. For more details, see the [Options](#id228ID8006H8) menu.

    -   **Show File Name**

        Shows the filename of the titles of the topics.

        >[!NOTE]
    >
    > When you hover your pointer over a topic's title, you are shown the file path.


**View topics based on conditional filters**If you have applied any conditions on a topic, a filter icon is displayed on the right of the topic. When you hover your pointer over a filter icon, you are shown the applied condition and its attribute value.

**Options menu in the Layout view**

In addition to organizing topics in the map file, you can also perform the following actions using the Options menu available for an element in the Layout view:

![](images/map-editor-options-menu.png)

-   **Add**: You can choose to add a new topic or an empty reference from the Map Editor:
    -   **Empty Reference**: This option allows you to add an empty reference in your DITA map. You can double-click the inserted empty reference later and add the Topic details. For more details, see the [Create a topic](web-editor-features.md#id228ICI0105U) in the Web Editor.
    -   **New Topic**: When you choose to create a new topic from the menu, you get the Create New Topic dialog. In the Create New Topic dialog, provide the required details and click Create. For more details, see the [Create a topic](web-editor-features.md#id228ICI0105U) in the Web Editor.
-   **Move**: You can choose to move a topic up/down/right/left in the hierarchy.You can also drag-and-drop a topic or a map from the repository panel to the map opened in the Map Editor.
-   **Undo**: Undo the last operation in the Layout view.
-   **Redo**: Redo the last operation in the Layout view.
-   **Copy**: Copy the selected reference from the map file.

    >[!NOTE]
    >
    > You can show and then select the checkboxes to copy multiple references.

-   **Paste**: Paste the copied references at the current location in the hierarchy.
-   **Delete**: Delete the selected references from the map file.

    >[!NOTE]
    >
    > You can show and then select the checkboxes to delete multiple references.


## Right Panel in the Map Editor 

The right panel displays the Content Properties and the Map Properties in the Layout view of the Map Editor.

Content Properties
:   The Content Properties panel contains information about the type of currently selected topic in the map, its link URL, and its attributes. For more details, see [Content Properties](web-editor-features.md#id228IDB00HMM) in the Web Editor.

    -   **Other Attributes** If your administrator has created a profile for attributes, then you'll get those attributes along with their configured values. Using the content properties panel, you can choose those attributes and assign them to relevant content in your topic. You can also assign inline attributes configured by your administrator under the Inline Attributes tab in the editor settings. The **Inline Attributes** defined for a topic are displayed against the topic in the Layout view. This helps you to have a quick look at all the topics in a map for which a particular attribute is defined. For example, all topics which have the platform attribute defined as 'Android'.

        ![](images/layout-inline-attributes.png)

        For more details, see [Inline Attributes](web-editor-features.md#id228IC0S0UE8) in the Editor Settings.

    -   **Metadata** Using the metadata , you can set the metadata information. You can define the Nav Title, Link Text, Short Description, and Keywords.

    For more information about the standard topic attributes and metadata, see the [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentation in OASIS DITA Language Specification.

Map Properties
:   Displays the Map Properties dialog wherein you can set the attributes and metadata information for the map.

## Author view {#id205DEC0005Z}

The **Author** view allows you to edit your DITA map in the Web Editor. This shows the WYSIWYG view of the Map Editor and some of the icons displayed in Author view are same as the Layout view. For more details, see [Layout view](#id205DEC0005Z). In addition, you can see the following icons and perform the related tasks from the Author view:

Insert Before/Insert After – ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)
:   Displays the Insert Element dialog. Select the element that you want to insert in the map. Depending on the operation, the new element is inserted before or after the current element in the map.

Insert Element – ![](images/Add_icon.svg)
:   Displays the Insert Element dialog. Select the element that you want to insert. You can use the keyboard to scroll through the list of elements and press Enter to insert the required element. Alternatively, you can click directly on the element to insert it in the map.

Insert Relationship Table – ![](images/relationship_table_icon.svg)
:   Inserts a relationship table in the map. As the concept of working with the relationship table is same as explained in the Basic Map Editor section, see [Work with relationship tables in the Basic Map Editor](map-editor-basic-map-editor.md#id1944B0I0COB) for more details.

Insert Reusable Content – ![](images/content-reuse-icon.png)
:   Displays the Reuse Content dialog. Use this dialog to insert the content that you want to reuse in your map.

Refresh Navigation Title Attribute – ![](images/navtitle-refresh-icon.svg)
:   Synchronizes the `title` element of a referenced file in a map with the value specified in its `@navtitle` attribute. You can add different types of reference files in a map, for example topic, reference, task, \(sub\) maps, and so on. Most of these files support the `@navtitle` attribute. If a file contains the `@navtitle` attribute, then the`@navtitle` attribute for the same file in map is updated. In case the `@navtitle` attribute is not present, then the`@navtitle` attribute is added to that reference file and its `title` is also updated to display the `@navtitle`.

    >[!NOTE]
    >
    > Your administrator can configure auto-adding `@navtitle` attribute to every reference file that you add to a map. For more details about configuring auto-adding `@navtitle` attribute, see *Include @navtitle attribute by default* in Install and configure Adobe Experience Manager Guides as a Cloud Service.

    Click the Refresh Navigation Title Attribute icon to synchronize the `title` element's and `@navtitle` attribute's values.

Toggle Tags View – ![](images/Label_icon.svg)
:   Shows or hides the XML tags. The tags serve as visual cues indicating an element's boundary. In this mode, if you want to insert a topic/map reference, then drag-and-drop the desired file before or after the tag. The horizontal bar is not shown in the Tags View mode.

Enable/Disable Track Changes ![](images/track-change-icon.svg)
:   You can keep a track of all updates made in the map file by enabling the Track Changes mode. After enabling the track changes, all insertions and deletions are captured in the document. For more details, see [Enable/Disable Track Changes](web-editor-features.md#id205DF0203Y4) in the Web Editor.

Create Review Task — ![](images/create-review-task-icon.svg)
:   You can create a review task of the current topic or map file directly from the Web Editor. Open the file for which you want to create the review task and click Create Review Task to initiate the review creation process. Follow the instructions given in the [Review topics or maps](review.md#) for more details.

## Edit topics through DITA map {#id17ACJ0F0FHS}

Editing an individual topic doesn't give the complete context to the author. An author would have no information about where a topic is placed in a DITA map. Without this contextual information, it becomes a bit difficult for authors to create content.

AEM Guides allows authors to open a DITA map in the Web Editor and see the placement of topics within the map. This helps authors to know where exactly the topic is placed within the map and create more relevant content. Also, if there are multiple authors working on a project, they can know what all topics are available in the map and reuse content, wherever required.

To edit topics through a DITA map, perform the following steps:

1.  In the Assets UI, navigate to the DITA map that contains the topics that you want to edit.

1.  Click on the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to see a list of topics available in the DITA map.

    >[!TIP]
    >
    > The Topics tab gives you an option to download the map file with its dependents. For more details, see [Export a DITA map file](authoring-download-assets.md#id218UBA00IXA).

1.  In the main toolbar, click **Edit Topics**.

    The DITA map opens in the Web Editor.

    >[!NOTE]
    >
    > You can also select the DITA map file in the Assets UI and click **Edit Topics** in the main toolbar to launch the Web Editor.

    ![](images/web-editor-map-view_cs.png)

1.  \(*Optional*\) You can also select a topic from the map and checkout the file before editing. To checkout file\(s\), select one or more files from the left pane and click **Checkout**. You can also release the lock on any file by selecting the checked out file and clicking on the **Cancel Checkout and Unlock** icon in the Map view.

    >[!IMPORTANT]
    >
    > If your administrator has configured the **Disable Edit Without Checkout** option, then you must check out the file before editing. If you do not checkout the file, then the document will open in the editor in read-only mode.

    The following screenshot highlights the icons for Checkout and Lock \(A\), Cancel Checkout and Unlock \(B\), Save As New Version and Unlock \(C\), Edit \(D\), Preview \(E\), different icons showing different DITA file types \(F\), and files that are checked out \(G\).

    ![](images/file-checkout-map-editor.png)

1.  Click on any topic link to open it in the Web Editor for editing.

    You can open multiple topics in the editor and each topic is opened in a new tab in the editor. Even if your DITA map contains sub-maps, topics from the sub-maps are also opened in a new tab for editing. If you want to view the topics under a sub-map, you can click and expand the sub-map.

    ![](images/web-editor-multiple-topics.png)

    If you click a map file, the map is opened in a new tab of the web browser.

1.  Once you have finished editing the topics, you can do the following:

    -   You can save them individually. If you click on **Close Without Saving** your topics, you will see a dialog prompting you to save the unsaved topics:

        ![](images/save-multiple-topics.PNG)

        You can choose to save all selected topics or deselect the topics that you do not want to save.

    -   You can check in the topic using the **Save As New Version and Unlock** button. When you save a revision of the topic, a new revision is created and the lock is also release.
    -   If your administrator has enabled the option of checking in files on close, then you will be shown a prompt to save files whenever the checked out files are closed. With this option enabled, when you close the editor with changed files, you are shown the list of checked-out files that need to be saved. The checked out files are shown with a lock icon:

        ![](images/save-on-close.PNG)

        -   Clicking on **Close Without Saving** button closes the files without saving any changes.

        -   Clicking the **Save** button saves the changes, but does not check in the files.

        -   Selecting the **Checking Files** option and then clicking the **Save** button checks in the files \(creates another version\) and also saves the files.


## Preview a map 

In addition to be able to see the position of each topic file within a map, it is desirable to see the map content in one consecutive flow. The Preview Map feature allows you to see the entire content of the map file in a single click. You don't have to generate an output of the map file to see how the entire map will look like once published. You can simply access the map's preview and all topics and sub-maps are rendered in the form of a book.

You can access a map's preview from:

-   **Assets UI**: In the Assets UI, navigate to the map location, select the map file, and choose **Preview Map** in the Toolbar. The map's preview is shown in a new tab. You can view the content of all topics in the preview mode. In this view, you cannot edit any topic.

    >[!NOTE]
    >
    > If the *Preview Map* option is not visible in the main toolbar, it might have moved under the **More** toolbar menu.

-   **Advanced Map Editor**: In the Advanced Map Editor, click on the Preview icon to see the preview of the current map.

    ![](images/map-preview-icon.png)

    You can perform the following additional tasks in the preview mode:

    -   Right-click on a topic, and select **Edit** to open the topic for editing in a new tab.

        >[!NOTE]
        >
        > If you don't have editing rights, then the topic will open in read-only mode.

    -   Jump to the desired topic by clicking on the topic title in the map tree \(in left panel\).

    -   The current topic in map preview is also highlighted in the map tree.


**Parent topic:**[Work with the Map Editor](map-editor.md)

