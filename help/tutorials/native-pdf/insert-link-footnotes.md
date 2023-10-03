---
title: Native PDF | Support for language variables
description: Learn how to insert the footnote references and link them to the footnote text. Apply CSS styles on the footnote references.
---

# Insert and link footnotes 

Footnotes are notes placed on the bottom of the page in a PDF. Footnotes generally provide references or details that would break the flow of the main content. For example, citations or additional notes. 

A footnote consists of two parts:  

* The footnote call or reference that appears in the text. 

* The footnote text contains further details and appears at the bottom of the page.  

 

## Insert a footnote 

To insert a footnote reference in your main content, use the `<fn>` element. In the authoring mode, the footnote reference value is shown in line with the content. However, in the **Preview** mode or the output of your document, the footnote text appears at the end of the topic. The footnote references are indicated in the text with markers like superscript numbers.  

>[!NOTE]
>
> The footnotes appear in a sequence according to their location in the main content. So, the first reference in the main content occurs as the first footnote. 

 

## Add reference links for a footnote 

You can also link the footnotes. To link the footnotes, you can create footnotes with IDs and then refer to them across the content. The footnote markers appear as links for the footnote references.  

 

Perform the following steps to create IDs for the footnotes and then refer to them:   

1. Select the footnote in the content. 

1. Add the **id** attribute and define a unique value from the content properties panel. 

1. To refer to the footnote, select <img src="./assets/Reference_icon.svg" width="25"> from the secondary toolbar and add a content reference in the main content.  

1. To add a reference to the footnote, add the **type** attribute and define the value as ‘fn’.  

 

This reference appears as a link to the footnote in the PDF output. You can refer to the same footnote multiple times in your PDF output. This helps you refer to the same citation or detailed note various times in the document without creating a footnote for it again. 

 

For example, the following screenshot shows how the same footnote is linked to all cities in the PDF output. 

<img width="550" alt="footnote references in a pdf" src="./assets/link-footnotes.png"> 

*Insert a footnote refrence and link it to the footnote text.*


## Footnote styles

You can apply CSS styles to footnotes. For example, you can hide a footnote or change the color of a footnote reference.

### Hide a footnote 

You can also apply a style to hide the footnotes with the IDs. When you hide a footnote, the footnote call or reference is hidden in the main content, but the footnote text appears at the bottom of the page.  

Use the following style to hide a footnote with the IDs: 

```
.fn[id]::footnote-call { 
display: none; 
} 
```
 

### Format footnote references 

Using CSS styles, you can also format the footnote references. For example, you can change the background color of footnote references. 

```
.xref-fn{ 
background-color: red; 
} 
```
 

 

 