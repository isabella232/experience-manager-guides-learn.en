---
title: Native PDF Publish Feature | Add a custom bookmark in PDF output
description: Learn how to create use styleheets and create styles for your content.
---

# Add a custom bookmark in PDF output

Generally, the TOC in a DITA map is replicated as bookmarks in the final PDF output. This TOC is created from the topic or section titles in your DITA map. At times you may want to add a custom bookmark on a particular content in your PDF output for easy navigation. This can be achieved by adding an `outputclass` attribute on the element and applying the following attribute to it: 

`bookmark-level: 3`

Here, the `bookmark-level` is an attribute and number `3` is the value that indicates the level in the bookmark hierarchy where the bookmark is added. In the following example, the first-level topic "Contacts" has a table, "Contact list" on which we have added an `outputclass` attribute with the value of `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width=500>

The following definition of the `custom-bookmark` class is added in the CSS file:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

In the PDF output, the *Contact list* table is added at the 2nd level in the PDF bookmark list, as shown below:

<img src="./assets/custom-bookmark-in-pdf-output.png" width=500> 

>[!NOTE]
>
>You must choose the correct level where the custom bookmark is added. If you specify a number that's less than the parent topic's bookmark, then the custom bookmark takes the position of the parent bookmark and all other bookmarks are shown as children. This can lead to unexpected bookmark structure. 

