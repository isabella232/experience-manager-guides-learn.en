---
title: Customize toolbar
description: Learn how to Customize toolbar
---

# Customize toolbar {#id172FB00L0V6}

By default, the Web Editor is shipped with the most common editorial features required by any DITA editor. Features such as inserting elements of type list \(numbered or bulleted\), cross-reference, content reference, table, paragraph, and character formatting are available in the editor. In addition to these basic elements, you can customize the Web Editor to insert elements that are used in your authoring environment.

There are two ways of customizing the Web Editor's toolbar:

-   Add a new functionality to the toolbar

-   Remove any existing functionality from the toolbar


## Add a feature in the toolbar 

Adding a functionality to the Web Editor involves two primary tasks - adding an icon for the feature in the *ui\_config.json* file and adding the background functionality in JavaScript.

Perform the following steps to add a feature to the Web Editor's toolbar:

1.  To download the UI configuration file log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides**from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click **Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system. You can then make changes to the file and then upload the same.
1.  In the `ui_config.json` file, add the definition of the new feature in the toolbars section. Save the file and upload it.

    Typically, you can create a new toolbar button group and add one or more toolbar buttons to it. Or, you can add a new toolbar button within an existing toolbar group. The following details are required to create a new toolbar group:

    type
    :   Specify `blockGroup` as the `type` value. This value indicates that you are creating a block group that would contain one or more toolbar groups.

    extraclass
    :   Name of the class or classes separated with space.

    items
    :   Specify the definition of all groups in the toolbar. Each group can contain one or multiple toolbar icons. To define icons within a toolbar group, you need to again define the `type` attribute within the `items`, and set its value to `buttonGroup`. Specify one or more class names in the `extraclass` property. Specify the feature name in the `label` property. The following snippet from the `ui_config.json` file shows the definition for the main toolbar block, followed by the `buttonGroup` definition:

        ```
        "toolbar": {    
        ```

        ```
        "type": "blockGroup",    
        ```

        ```
        "extraclass": 
        ```

        ```
        "toolbar operations",    
        ```

        ```
        "items": [      
        ```

        ```
        {        
        ```

        ```
        "type": "buttonGroup",        
        ```

        ```
        "extraclass": "left-controls",        
        ```

        ```
        "label": "Left Controls",        
        ```

        ```
        "items": [
        ```

        ```

        ```

    :   Within the `items` collection, you need to specify the definition for one or more toolbar icons.

    You need to define the following properties to add a toolbar icon:

    type
    :   Specify `button` as the `type` value. This value indicates that you are adding a toolbar button.

    icon
    :   Specify the name of the Coral icon that you want to use in the toolbar.

    variant
    :   Specify `quiet` as the `variant` value.

    title
    :   Specify the tooltip for the icon.

    on-click
    :   Specify the command name defined for the feature in the JavaScript file. If your command requires input parameters, then specify the command name as:

        ```
        "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
        ```

    show or hide
    :   If you are defining the `show` property, then specify the modes in which the icon is displayed. Possible values are - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(display in all modes\), or `false` \(hide in all modes\).

        In place of `show`, you can also define the `hide` property. The possible values are same as in `show` property with the only difference that the icon is not displayed for the specified mode.

    The following example shows AEM Guides version number when the user clicks on the Show Version icon in the toolbar.

    Add the following code to a JavaScript file:

    ```
    $(document).ready(setTimeout(function() {
                            fmxml.commandHandler.subscribe({
                            key: 'user.alert',
                            next: function() {
                            alert("AEM Guides version x.x")
                            }
                            })
                            }, 1000))
    ```

    Add the feature in the *ui\_config.json* file as:

    ```
    "type": "button",
    ```

    ```
    "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
    ```

1.  Create a *clientlib* folder and add your JavaScript into this folder.

1.  Update the categories property of the *clientlib* folder by assigning it the value of *apps.fmdita.xml\_editor.page\_overrides*.

1. Save the *ui\_config.json* file and reload the Web Editor.


## Remove a feature from the toolbar 

At times you might not want to give all features currently available in the Web Editor, in that case you can remove the unwanted feature from the Web Editor's toolbar.

Perform the following steps to remove any unwanted feature from the toolbar:

1.  To download the UI configuration file log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click **Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system. You can then make changes to the file and then upload the same.

    The `ui_config.json` file has three sections:

1.  toolbars
:   This section contains the definition of all features available in the editor's toolbar such as Insert/Remove Numbered List, \(file\) Close, Save, Comments and more.

shortcuts
:   This section contains the definition of keyboard shortcuts assigned to a particular feature in the editor.

templates
:   This section contains the predefined structure of DITA elements that you can use in your document. By default, the templates section contains template definitions for a paragraph, simple table, table, and body elements. You can create a template definition for any element by adding a valid XML structure for the desired element. For example, if you want to add a `p` element with every new `li` element in a list, you can add the following code at the end of the templates section to achieve this:

    ```
    "li": "<li><p></p></li>"
    ```

1.  From the toolbars section, remove the entry of the feature that you do not want to expose to your users.

1.  Save the *ui\_config.json* file and reload the Web Editor.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)

