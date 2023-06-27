---
title: Customize AEM's default dictionary
description: Learn how to Customize AEM's default dictionary
---

# Customize AEM's default dictionary {#id209SD8000WU}

The Web Editor can be configured to use AEM's spell checker or the browser's spell checker. If you choose to work with AEM's spell checker, then you get the flexibility to define your custom words list. These custom words are then added to the AEM's dictionary and these words are not flagged \(as incorrect\) in the Web Editor.

Perform the following steps to create your custom words list, which are added in AEM's dictionary:

1.  Create user\_dictionary.txt file with a list of words that you want to define in your custom dictionary.

    >[!NOTE]
    >
    > Each custom word must be defined on a new line.

1.  Save the file at the following location in your Cloud Manager's Git repository:

    /apps/fmdita/config

1.  Save the file.

    Commit the changes and run the Cloud Manager \(CI/CD\) pipeline to deploy configuration changes.


Authors would need to restart their Web Editor session to get the custom words list updated in AEM dictionary.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

