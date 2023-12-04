---
title: Release Notes | What's New in the Adobe Experience Manager Guides, November 2023 release
description: Learn the new and enhanced features in November 2023 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the November 2023 release of Adobe Experience Manager Guides as a Cloud Service

This article covers the new and enhanced features in the version  November 2023 of Adobe Experience Manager Guides (later referred to as *Experience Manager Guides as a Cloud Service*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, view [Release notes](release-notes-2023.11.0.md).

## Native PDF enhancements

The following Native PDF enhancements have been done in the November 2023 release:

### Use and duplicate out-of-the-box PDF templates 

Experience Manager Guides provides out-of-the-box  or factory PDF templates. Duplicate the factory PDF templates to create the custom PDF templates.

Now, you can also preview the thumbnail image for a template while creating and duplicating a template. You can also edit or delete this image. This feature is useful for branding or distinguishing templates with similar names.
Learn more about the [PDF template](../native-pdf/pdf-template.md).
 
![Duplicate PDF template dialog](assets/duplicate-template.png){width="550" align="left"}

*Duplicate an existing PDF template.*


### Change the order of pages and publish multiple pages per sheet

Besides publishing the pages according to the source document, you can also change the order of pages in PDF while publishing a multi-page document.  This gives you the flexibility to publish the pages in various orders, like all odd, or all even pages first. You can also publish as a booklet and read the pages like a book. You can also decide the number of pages you want to publish on a single sheet of paper. For more details, view the [Page Organization](../native-pdf/components-pdf-template.md#page-organization) section. 

### Sort glossary terms based on sort keys

Now, you can also sort the glossary terms based on sort keys. You can use the tag ‘sort-as’ to define a sort key for the glossary terms. Then, you can sort them based on sort keys in place of the terms. This allows you to sort the glossary terms according to terms used in different languages. You can also define a single sort key for a glossary term with a phrase or a group of words. 
For more details, view the [Advanced PDF Settings](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Improved resource management for Native PDF templates 

Experience Manager Guides now has improved the resource management for Native PDF templates. You can now share and reuse resources, like images, CSS files, and font files, across multiple Native PDF templates. With this improvement, managing the resources for a large set of templates is much simpler. You don't need to create duplicate resources for each template, and you can keep them in a shared folder and use them in all Native PDF templates.
For more details, view [PDF Template](../native-pdf/pdf-template.md). 

## Web Editor enhancements

The following Web Editor enhancements have been done in the November 2023 release:


### View files by title or filenames 

You can now choose the default way to view the files in the Web Editor. You can view the list of files by the titles or the filenames from the various panels from the Author view.

![User Preferences dialog](assets/user-preferences-2311.png){width="550" align="left"}

*Change the default way to view the files from the **User Preferences** dialog.*
 

### Manage condition presets 

You can define condition attributes in your DITA topics. Then, use the condition attributes in the condition preset to publish the content in a DITA map. Experience Manager Guides now also allows you to create and manage condition presets from the Web Editor. You can also easily edit, duplicate, or delete them.

![Condtion Presets from the Manage tab of the Web editor ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

For more details, view [Use condtion presets](../user-guide/generate-output-use-condition-presets.md).

### Restore file tabs on refreshing the browser

Experience Manager Guides restores the state of the opened file tabs in the Web Editor when you refresh the browser. For more details, view the **Refresh browser while editing the files** section under [Edit topics in the Web Editor](../user-guide/web-editor-edit-topics.md).

### Unwrap an element easily 

Now you can easily unwrap an element using the option from the context menu of an element in the Web Editor. This helps you easily merge the element's text with its parent element. 
For more details, view the **Unwrap an element** section from the [other features in the Web Editor](../user-guide/web-editor-other-features.md). 

### Keyboard shortcuts to move the cursor 

Experience Manager Guides now also allows you to use keyboard shortcuts to move the cursor in the Web Editor. You can use the keyboard shortcuts to quickly move one word left or right. You can also move to the beginning or the end of the line with the help of the keyboard shortcuts.
Now, you can also use keyboard shortcuts to move the cursor to the beginning of the next element or the end of the previous element.
Learn more about the [keyboard shortcuts in the Web Editor](../user-guide/web-editor-keyboard-shortcuts.md).
