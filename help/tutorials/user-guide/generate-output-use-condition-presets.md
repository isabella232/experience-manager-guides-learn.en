---
title: Use condition presets
description: Know the use of condition presets in AEM Guides. Learn to create, edit, copy, and delete condition presets in AEM.
exl-id: cd8f8196-ba03-4a4b-9ce8-2651de4e5cc2
---
# Use condition presets {#id1825FL004PN}

You can define attributes in your DITA topics and the use the condition preset to specify what happens with the attribute in the final output. For example, you can add attributes as version 1.0 and version 2.0 in your content, and use a condition preset to include version 1.0 for release 1.0 and exclude version 2.0. Similarly, you can add attributes as OS Windows and OS Linux to your content, and then include or exclude the relevant content for your final output according to the operating system.

You can create condition presets in two ways:

* From the Web Editor: Allows you to create and manage the condition presets for a DITA map from the Web Editor. 
* From the map dashboard: Allows you to create and manage the condition presets for a DITA map from the map dashboard.


## Condition presets from the Web Editor

Experience Manager Guides allows you to manage condition presets from the Web Editor and use them within the Output presets to generate the final output.
You can create and view the condition presets, view the attributes, and manage the actions for the current map from the **Condition Presets** view in the Web Editor.

<img src="images//manage-condtions-presets.png" alt= "Condtion presets in web editor" width="800" border="1px">



### Create a condition preset

The **Condition Presets** view provides detailed information about the condition presets, such as their attributes, values,  and the actions.
You can create a condition preset of the topics by performing the following steps:

1. In the **Repository** panel, open the DITA map file in Map View.
1. Select the **Manage** tab.
1. Select **Condition Presets** on the left. The list of conditions presets defined for the DITA map is displayed.
1. Select the + icon next to **Condition Presets** to open the **New Condition Preset** dialog. 
1. Enter a unique name for the preset.
 
    >[!NOTE]
    >
    > You view an error if the name field is empty or if you enter an Invalid character or a name that is the same as an existing condition preset. You can use a hyphen '-' or underscore '_' as a separator.

1. Select **Create**.
The new condition preset is added to the list.
1. Double-click a condition preset to view the attributes and the actions.
The **Attributes** panel shows all the attributes added to the map. The right panel shows only the conditions that are selected.
1. Do any of the following to add the attributes:
    * Select one or more attributes to add all the values under them to the condition preset. For example, you can select the `platform` attribute to add all its values.
    * Select one or more attribute values to add them to the condition preset. For example, you can select the `Unix` and `Win` values of the platform attribute 
    * **Select all** to add all the attributes and their values to the condition preset.
    By default, the action for an attribute is `Include`.

1. Select **Add**. You can repeat this step to add more attributes. The attributes that you add move from the central to the right panel.  
1. Select Remove from the actions bar on the top to remove the selected attributes in the right panel. 
1.  (Optional) If required, you can override the action applied to the attributes. 
Do one of the following:
    * For any attribute, select one of the following actions from the Action drop-down.
        * Include
        * Exclude
        * Passthrough
        * Flag
    * Select multiple attribute rows from the right panel and choose an action from the actions bar on the top. For example, you can select Exclude action for the selected attributes.
1.  Select **Save** to save the condition preset. 

    >[!NOTE]
    >
    > You view a warning if you select another preset or close the preset without saving it. 

Once you create a condition preset, it appears under the **Condition Presets** dropdown of the Output presets. Learn more about how to [Publish PDF output](../web-editor/native-pdf-web-editor.md). 

### Rename a condition preset

Perform the following steps to rename a condition preset:

1. Hover over a condition preset from the **Condition Presets** panel.
1. Select **Rename** from the Options menu to open the **Rename condition preset** dialog.
1. Edit the name of the condition preset.
1. Click **Rename**.

### Duplicate a condition preset

Perform the following steps to duplicate a condition preset:

1. Hover over  a condition preset from the **Condition Presets** panel.
1. Select **Duplicate** from the Options menu to open the **Duplicate condition preset** dialog.
    >[!NOTE]
    >
    > The default name of the preset is `<selected condition preset name>_1`. You can change the name according to your requirements.
    
1. Click **Duplicate**.

### Delete condition preset

Perform the following steps to delete condition presets:

1. Hover over  a condition preset from the **Condition Presets** panel.
1. Select **Delete** from the Options menu to open the **Delete condition preset** dialog.
1.  Click **Delete**.



## Condition presets from the map dashboard


### Create a condition preset 

Perform the following steps to create a condition preset:

1.  Select **Condition Presets** tab in the DITA map console.
1.  Click **Create** button.
1.  Enter a name for the preset in **Name Condition**.
1.  Select one of the following default actions from **Set default action to** drop-down:

    *   Include
    *   Exclude
    *   Passthrough
    *   Flag
    The action is set as default action for all the attributes whether they are added to the condition preset or not.

    For example, you have 15 condition attributes in your document and you have included four of them in the condition preset. If you select **exclude** as default action, it is applied to all 15 attributes.

1.  Do any of the following to add the attributes:
    *   Click **Add** to one attribute to the condition preset. You can repeat this step to add more attributes.
    *   Click **Add all** to add all the attributes to the condition preset.
1.  \(Optional\) If required, you can override the default action applied to the attributes in Step 4. Do one of the following:
    *   Select multiple attributes, choose an action from **Set the action for selected conditions to**, and click **Apply**.
    *   Select an action for an attribute from the **Action** drop-down.
1.  Click **Save**.

### Edit a condition preset 

You can make changes in an existing condition preset to change the actions applied to the attributes in the condition preset. Perform the following steps to edit a condition preset:

1.  Select **Condition Presets** tab in the DITA map console.
1.  Click **Edit** button.
1.  Make required changes for all the attributes in the condition preset.
1.  Click **Save**.

### Create a copy of a condition preset 

You can create a copy of a condition preset and then modify it according to your requirement. Perform the following steps to create a copy of a condition preset:

1.  Select **Condition Presets** tab in the DITA map console.
1.  Click **Duplicate** button.

    >[!NOTE]
    >
    > The default name of the preset is `<selected condition preset name>_Duplicate`

    You can change the name according to your requirement.

1.  \(Optional\) Make required changes for all the attributes in the condition preset.
1.  Click **Save**.

### Delete condition preset 

You can delete one or more condition presets from the **Condition Preset** tab of the DITA map console. Perform the following steps to delete condition presets:

1.  Select **Condition Presets** tab in the DITA map console.
1.  Select the condition preset\(s\) that you want to delete.
1.  Click **Remove** button.
1.  Click **Remove** to confirm the action.

**Parent topic:**[Output generation](generate-output.md)
