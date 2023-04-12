---
title: DITAVAL editor
description: Learn how to DITAVAL editor
---

# DITAVAL editor {#id17C5E0U0OQE}

DITAVAL files are used to generate conditional output. In a single topic, you can add conditions using element attributes to conditionalize content. Then, you create a DITAVAL file wherein you specify the conditions that should be picked up to generate content, and which condition should be left out from the final output.

AEM Guides allows you to easily create and edit DITAVAL files using the DITAVAL editor. The DITAVAL editor retrieves the attributes \(or tags\) defined in your system, and you can use them to create or edit DITAVAL files. For more details about creating and managing tags in AEM, see [Administering Tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) section in AEM documentation.

## Create DITAVAL file 

Perform the following steps to create a DITAVAL file:

1.  In the Assets UI, navigate to the location where you want to create the DITAVAL file.

1.  Click **Create** \> **DITA Topic**.

1.  On the Blueprint page, select DITAVAL file template and click **Next**.

1.  On the Properties page, specify the **Title** and **Name** for the DITAVAL file.

    >[!NOTE]
    >
    > The name is automatically suggested based on the Title of your file. If you want to manually specify the file name, then ensure that the Name does not contain any spaces, apostrophe, or braces and ends with `.ditaval`.

1.  Click **Create**. The Topic Created message appears.

    You can choose to open the DITAVAL file for editing in the DITAVAL editor, or the save the topic file in the AEM repository.


## Edit DITAVAL file 

Perform the following steps to edit a DITAVAL file:

1.  In the Assets UI, navigate to the DITAVAL file that you want to edit.
1.  To get an exclusive lock on the file, select the file and click **Check Out**.
1.  Select the file and click **Edit** to open the file in AEM Guides DITAVAL editor.

    The DITAVAL editor allows you to perform the following tasks:

    **A: Toggle Left Panel**

    Toggle the left panel view. If you have opened the DITAVAL file through DITA map, the map and repository are shown in this panel. For more information about opening a file through DITA map, see [Edit topics through DITA map](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

    **B: Save**

    Saves the changes you have made in the file. All your changes are saved in the current version of your file.

    **C: Add Property**

    Add a single property in your DITAVAL file.

    ![](images/ditaval-editor-props.png)

    The first drop-down lists the allowed DITA attributes that you can use in the DITAVAL file. There are five attributes that are supported - `audience`, `platform`, `product`, `props`, and `otherprops`.

    The second drop-down list shows the values configured for the selected attribute. Then, the next drop-down list shows the actions that you can configure on the selected attribute. The allowed values in the action drop-down are - `include`, `exclude`, `passthrough`, and `flag`. For more information about these values, see the definition of [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) element in OASIS DITA documentation

    **D: Add All Properties**

    If you want to add all conditional properties or attributes defined in your system with a single click, use the Add All Properties feature.

    >[!NOTE]
    >
    > If all defined conditional properties already exist in the DITAVAL file, you cannot add more properties. You get an error message in this scenario.

    ![](images/ditaval-all-props.png)

1.  Once you have finished editing your DITAVAL file, click **Save**.

    >[!NOTE]
    >
    > If you close the file without saving, the changes will be lost. If you do not wish to commit changes into AEM repository, click **Close**, and then click **Close Without Saving** in the **Unsaved Changes** dialog.


## DITAVAL editor views 

AEM Guides' DITAVAL editor supports viewing DITAVAL files in two different modes or views:

**Author** - This is a typical What You See is What You Get \(WYSISYG\) view of the DITAVAL editor. You can add or remove properties using the simple user interface, which presents the properties, its values, and actions in drop-down list. In the Author view, you have the options to insert an individual property and insert all properties with a single click.

You can also find the version of the DITAVAL file that you are currently working on by hovering your pointer over the filename.

**Source** - The Source view displays the underlying XML that makes up the DITAVAL file. In addition to making regular text edits in this view, an author can also add or edit properties using the Smart Catalog.

To invoke the Smart Catalog, place the cursor at the end of any property definition and enter "<". The editor will show a list of all valid XML elements that you can insert at that location.

![](images/ditaval-source-view.png)

**Parent topic:**[Author content using AEM Guides](authoring-content-xml-doc.md)

