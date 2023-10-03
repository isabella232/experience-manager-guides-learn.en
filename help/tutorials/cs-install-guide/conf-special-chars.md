---
title: Configure allowed special characters
description: Learn how to Configure allowed special characters
exl-id: d3430009-b7a7-4ecb-a19b-dd75305014a9
---
# Configure allowed special characters {#id20CIL600035}

The Web Editor allows you to insert some special characters out-of-the-box. However, you can customize the list of special characters that your authors can insert in their documents. If you customize the special characters list, then it overwrites the default set of special characters. Only those special characters that you add in your configuration are made available to the authors.

Perform the following steps to overwrite the default list of special characters:

1.  Create `symbols.json` file at the following location in your Cloud Manager's Git repository:

    ```
    /apps/fmdita/xmleditor/
    ```

1.  Add the special character definition in the `symbols.json` file as:

    ```
    {"symbols": [{"label": "Arrows",
       "items": [
       {   "name": "←",   "title": "Left Arrow"   } 
       ,   
       {   "name": "↑",   "title": "Up Arrow"      } 
       ]   
       }   ]   }
    ```


The structure of the `symbols.json` file is explained below:

-   `"label": "Arrows"`: This specifies the category for the special characters. In the snippet, a category with the name `"Arrows"` is defined.
-   `"items"`: This defines the collection of special characters in the category.
-   `"name": "←", "title": "Left Arrow"`: This is the definition of the special character. It starts off with the `"name"` label, which must not be changed. The name is followed by the special character. The `"title"` is the name or title of the special character that appears as the tooltip for that special character.

    You can define multiple definitions of special characters within a category.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
