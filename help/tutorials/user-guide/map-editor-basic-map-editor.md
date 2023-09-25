---
title: Work with the Basic Map Editor
description: Learn how to work with the Basic Map Editor in AEM Guides. Know the features of the basic map editor at map level and topic level. Create and edit relationship tables in  a DITA map.
exl-id: 85194806-db3f-442b-a551-540d148d26ec
---
# Work with the Basic Map Editor {#id1942CM005Y4}

The Basic Map Editor provides an easy drag-and-drop feature to add topics from your AEM repository to create the DITA map or bookmap. You can add nested topics, relationship tables \(reltable\), attributes and metadata information, and also validate the map for correctness.

>[!NOTE]
>
> If your administrator has enabled the Advanced Map Editor option, then you will not have access to the Basic Map Editor. All map files will open in the Advanced Map Editor by default.

The following sections describe the various functions available in the Basic Map Editor.

## Add topics to a map file {#id193CBL0505Z}

Once a map file is created, you need to add topics to the map file. Using the Basic Map Editor, you can add topics, relationship tables, or other map files.

Perform the following steps to build your map file:

1.  In the Assets UI, navigate to the map file that you want to edit.

1.  To get an exclusive lock on the map file, select the map file and click **Check Out**.

    >[!NOTE]
    >
    > Once you have an exclusive lock on a map file, other users would not be able to edit the map. However, they would be able to work on the topics within the map file.

1.  With the map file selected, click **Edit**.

    The map file is opened for editing in the Map Editor. Using the Map Editor, you build a map by using the currently available topics that are displayed in the References rail.

    ![](images/dita-map-01.png){width="800" align="left"}

1.  Using the **References** rail, navigate to the folder that contains the topics or sub-maps that you want to add.

    >[!NOTE]
    >
    > You can add topics or sub-maps from any folder in the References rail.

1.  To add the first topic to the map, drag-and-drop the topic onto the Basic Map Editor.

    >[!NOTE]
    >
    > After adding the first link, the Add New Reference link is available when you hover your mouse over an existing topic in the map.

1.  To add subsequent topics or a sub-map, drag-and-drop the topic or sub-map to the required location in the map.

    If you add a sub-map to your DITA map, the sub-map is shown as a link in the DITA map. To view all the topics of the sub-map, click the sub-map link. The content of the sub-map are shown in a new tab.

    >[!NOTE]
    >
    > If you drop a new topic on an existing topic in the map, you get a message about replacing the topic. Click Yes if you want to replace the topic, click No if you do not want to replace the topic. You can use CTRL+Z and CTRL+Y to undo or redo any change in the map.

1.  Click **Save**.


## Features available in the Basic Map Editor's toolbar 

The main toolbar in the Basic Map Editor allows you to perform the following tasks:

![](images/ditamap-toolbar-actions.png){width="800" align="left"}

**A: Search**

You can search for and include the required topics from DAM. Clicking on this icon displays the Search dialog:

![](images/search-dita-map.png){width="800" align="left"}

Enter the keywords you want to search for, these keywords are matched in the topic's filename, content, and even attribute values. Once the search results are available, select the desired topic\(s\) and click the Check button to add the selected files at the end of your map structure. You can filter your search results by specifying Modify Date parameters.

**B: Group**
   
Click the checkbox to the left of the topics and click Group in the toolbar to group the selected topics. For more information about grouping topics, see the [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentation in OASIS DITA Language Specification.

**C: Delete**

Click the checkbox to the left of a topic and click Delete in the toolbar to remove the selected topics from the map.

**D: Show Numbers/Hide Numbers**

Display \(or hide\) numbering for the topics in the map.

**E: Validate**

Check whether the map is valid or has errors.

**F: Default Mode/XML Mode**

In the **Default Mode**, clicking a topic link shows the preview of the topic in a new tab. Clicking on the **Default Mode** icon changes its mode to **XML Mode**. In **XML Mode**, clicking anywhere in a topic row shows the underlying XML of topic references within the topic. In the source XML view, there is an **Auto Indent** option that reorganizes the XML code in presentable and easily readable format. In case you are editing a map manually, the source view also performs validation checks. In case your XML contains errors, the same gets highlighted in the **XML Mode** and you are not allowed to save the DITA map file. If you want to view the XML for the entire map, click anywhere outside the topic boundary.


**Note:** In the Default Mode you can use the keyboard shortcuts to undo \(`Ctrl+z`\) or redo \(`Ctrl+y`\) the last action.


![](images/dita-map-invalid-source.png){width="650" align="left"}

**G: Map Properties**

Display the Map Properties dialog wherein you can set the attributes and metadata information for the map. To add an attribute, click the **Add** button at the bottom-left corner of the dialog to get the **Attribute** drop-down list. From the list, select the attribute that you want to add. If the selected attribute has pre-defined values specified in the DTD, then those values would be presented in a new drop-down list. You can select the desired value from the drop-down list. If there is no pre-defined value, then you will be presented a text box to enter a value for the selected attribute.

![](images/map-properties.png){width="300" align="left"}

## Features available at topic level in the Basic Map Editor 

When you hover your mouse pointer over a topic or a sub-map file in the Basic Map Editor, you can perform the following tasks:

![](images/ditamap-actions.png){width="650" align="left"}

**A: Move Left or Move Right**

Click the left or right arrow icons' to move the topic left or right. Moving a topic in such a way makes it a child \(nest\) or sibling \(remove nesting\) with respect to the topic above it.

**B: Properties**

Click the Properties icon to open the Topicref Properties dialog. Using this dialog, you can set the topic attributes and metadata information. For more information about the standard topic attributes and metadata, see the [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentation in OASIS DITA Language Specification.


![](images/map-properties-metadata.png){width="350" align="left"}

**C: Add New Reference**

Click the Add New Reference icon to add a new reference as a sibling of the current topic.

**D: Add New Key Definition**

Click the Key icon to add a new key definition. Any overridden key or a key that has been already defined in the map appears in red. If you click the Properties icon on a key definition, you get the Keydef Properties dialog.

## Work with relationship tables in the Basic Map Editor {#id1944B0I0COB}

AEM Guides' map editors come with a powerful feature that allows you to create and edit relationship tables in your DITA map.

Perform the following steps to work with relationship tables in the Basic Map Editor:

1.  In the Assets UI, navigate to the DITA map in which you want to create the relationship table.

1.  Click on the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to see a list of topics available in the DITA map.

    >[!TIP]
    >
    > The Topics tab gives you an option to download the map file with its dependents. For more details, see [Export a DITA map file](authoring-download-assets.md#id218UBA00IXA).

1.  In the main toolbar, click **Edit**.

    The map file is opened in the Basic Map Editor.

1.  Select **Reltable** from the toolbar.

    ![](images/reltable.png){width="650" align="left"}

1.  Drag-and-drop topics from the topic list to the Reltable editor.

    >[!NOTE]
    >
    > You can add topics from any folder in the References rail.

    ![](images/create-reltable.png){width="550" align="left"}

1.  To add a header to your relationship table, click **Add Relheader**.

1.  To add a column to your relationship table, click **Add a Column**.

    ![](images/complete-reltable.png){width="550" align="left"}

1.  Click **Save**.


You can also perform the following actions from the relationship table editor:

**Delete rows or columns**

If you want to delete a column from your table, select the checkbox in the column header and click Delete. If you want to remove a row from table, select the checkbox in the first column of the respective row and click Delete.

**Delete a topic**

If you want to delete a topic from your table, click the cross icon next to the topic.

**Delete the relationship table**

If you want to delete the relationship table, click anywhere outside the relationship table and click Delete.

**Parent topic:**[Work with the Map Editor](map-editor.md)
