---
title: Customize AEM's default dictionary
description: Learn how to Customize AEM's default dictionary
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
---
# Customize AEM's default dictionary {#id209SD8000WU}

The Web Editor can be configured to use AEM's spell checker or the browser's spell checker. If you choose to work with AEM's spell checker, then you get the flexibility to define your custom words list. These custom words are then added to the AEM's dictionary and these words are not flagged \(as incorrect\) in the Web Editor.

Perform the following steps to create your custom words list, which are added in AEM's dictionary:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the following node:

    /apps/fmdita/config

1.  Create a new file named user\_dictionary.txt.

1.  Open the file and add a list of words that you want to define in your custom dictionary.

    The following screenshot shows custom words list added to the user\_dictionary.txt file:

    ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1.  Save and close the file.


Authors would need to restart their Web Editor session to get the custom words list updated in AEM dictionary.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
