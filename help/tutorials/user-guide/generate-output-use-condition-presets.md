---
title: Use condition presets
description: Learn how to Use condition presets
exl-id: cd8f8196-ba03-4a4b-9ce8-2651de4e5cc2
---
# Use condition presets {#id1825FL004PN}

You can define attributes in your DITA topics and the use the condition preset to specify what happens with the attribute in the final output. For example, you can add attributes as version 1.0 and version 2.0 in your content, and use a condition preset to include version 1.0 for release 1.0 and exclude version 2.0. Similarly, you can add attributes as OS Windows and OS Linux to your content, and then include or exclude the relevant content for your final output according to the operating system.

## Create a condition preset 

Perform the following steps to create a condition preset:

1.  Click **Condition Presets** tab in the DITA map console.
1.  Click **Create** button.
1.  Enter a name for the preset in **Name Condition**.
1.  Select one of the following default actions from **Set default action to** drop-down:

    -   Include
    -   Exclude
    -   Passthrough
    -   Flag
    The action is set as default action for all the attributes whether they are added to the condition preset or not.

    For example, you have 15 condition attributes in your document and you have included four of them in the condition preset. If you select **exclude** as default action, it is applied to all 15 attributes.

1.  Do any of the following to add the attributes:
    -   Click **Add** to one attribute to the condition preset. You can repeat this step to add more attributes.
    -   Click **Add all** to add all the attributes to the condition preset.
1.  \(Optional\) If required, you can override the default action applied to the attributes in Step 4. Do one of the following:
    -   Select multiple attributes, choose an action from **Set the action for selected conditions to**, and click **Apply**.
    -   Select an action for an attribute from the **Action** drop-down.
1.  Click **Save**.

## Edit a condition preset 

You can make changes in an existing condition preset to change the actions applied to the attributes in the condition preset. Perform the following steps to edit a condition preset:

1.  Click **Condition Presets** tab in the DITA map console.
1.  Click **Edit** button.
1.  Make required changes for all the attributes in the condition preset.
1.  Click **Save**.

## Create a copy of a condition preset 

You can create a copy of a condition preset and then modify it according to your requirement. Perform the following steps to create a copy of a condition preset:

1.  Click **Condition Presets** tab in the DITA map console.
1.  Click **Duplicate** button.

    >[!NOTE]
    >
    > The default name of the preset is `<selected condition preset name>_Duplicate`

    You can change the name according to your requirement.

1.  \(Optional\) Make required changes for all the attributes in the condition preset.
1.  Click **Save**.

## Delete condition preset 

You can delete one or more condition presets from the **Condition Preset** tab of the DITA map console. Perform the following steps to delete condition presets:

1.  Click **Condition Presets** tab in the DITA map console.
1.  Select the condition preset\(s\) that you want to delete.
1.  Click **Remove** button.
1.  Click **Remove** to confirm the action.

**Parent topic:**[Output generation](generate-output.md)
