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

**Add an icon in the toolbar**

Perform the following steps to add a feature to the Web Editor's toolbar:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1.  Create a copy of the default configuration file at the following location:

    `/apps/fmdita/xmleditor/ui_config.json`

1.  Navigate to and open the `ui_config.json` file in the `apps` node for editing.

1.  In the `ui_config.json` file, add the definition of the new feature in the toolbars section. Typically, you can create a new toolbar button group and add one or more toolbar buttons to it. Or, you can add a new toolbar button within an existing toolbar group. The following details are required to create a new toolbar group:

    type
    :   Specify `blockGroup` as the `type` value. This value indicates that you are creating a block group that would contain one or more toolbar groups.

    extraclass
    :   Name of the class or classes separated with space.

    items
    :   Specify the definition of all groups in the toolbar. Each group can contain one or multiple toolbar icons. To define icons within a toolbar group, you need to again define the `type` attribute within the `items`, and set its value to `buttonGroup`. Specify one or more class names in the `extraclass` property. Specify the feature name in the `label` property. The following snippet from the `ui_config.json` file shows the definition for the main toolbar block, followed by the `buttonGroup` definition:

        ```json
        "toolbar": {    
          "type": "blockGroup",    
          "extraclass": 
          "toolbar operations",    
            "items": [      
              {        
                "type": "buttonGroup",        
                "extraclass": "left-controls",        
                "label": "Left Controls",        
                "items": [
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

        ```JavaScript
        "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
        ```

    show or hide
    :   If you are defining the `show` property, then specify the modes in which the icon is displayed. Possible values are - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(display in all modes\), or `false` \(hide in all modes\).

        In place of `show`, you can also define the `hide` property. The possible values are same as in `show` property with the only difference that the icon is not displayed for the specified mode.

1.  Create a *clientlib* folder and add your JavaScript into this folder.

1.  Update the categories property of the *clientlib* folder by assigning it the value of *apps.fmdita.xml\_editor.page\_overrides*.

1.  Save the *ui\_config.json* file and reload the Web Editor.


**JavaScript code samples**

This section provides two examples of JavaScript code that would help you get started with adding custom functionality. The following example shows AEM Guides version number when a user clicks on the Show Version icon in the toolbar.

Add the following code to a JavaScript file:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Add the feature in the ui\_config.json file as:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

The following example shows how to change a document's state of an active file to "In-Review".

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Add the feature in the ui\_config.json file as:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Remove a feature from the toolbar 

At times you might not want to give all features currently available in the Web Editor, in that case you can remove the unwanted feature from the Web Editor's toolbar.

Perform the following steps to remove any unwanted feature from the toolbar:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:.

    `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1.  Create a copy of the default configuration file at the following location:

    `/apps/fmdita/xmleditor/ui_config.json`

1.  Navigate to and open the `ui_config.json` file in the `apps` node for editing.

    The `ui_config.json` file has three sections:

1.  toolbars
:   This section contains the definition of all features available in the editor's toolbar such as Insert/Remove Numbered List, \(file\) Close, Save, Comments and more.

shortcuts
:   This section contains the definition of keyboard shortcuts assigned to a particular feature in the editor.

templates
:   This section contains the predefined structure of DITA elements that you can use in your document. By default, the templates section contains template definitions for a paragraph, simple table, table, and body elements. You can create a template definition for any element by adding a valid XML structure for the desired element. For example, if you want to add a `p` element with every new `li` element in a list, you can add the following code at the end of the templates section to achieve this:

    ```HTML
    "li": "<li><p></p></li>"
    ```

1.  From the toolbars section, remove the entry of the feature that you do not want to expose to your users.

1.  Save the *ui\_config.json* file and reload the Web Editor.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)

