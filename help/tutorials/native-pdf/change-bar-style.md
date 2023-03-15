---
title: Native PDF Publish Feature | Work with custom change bars styles  
description: Learn how to apply styles on change bars.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
---
# Work with custom change bars styles

A change bar is a vertical line that visually identifies new or revised content. AEM Guides allows you to show a change bar on the left of the changed content within  topics and also the changed topics in the TOC of the PDF output.  

For more details on showing the change bar, see *Create PDF with Change Bar between Published Versions* setting in
[Publish PDF Output](../web-editor/native-pdf-web-editor.md).

## Changed content within topics

The change bar appears on the left of the content in the topics that has been inserted, changed, or deleted. 

You can modify the following styles to show the changed content and among with the change bars. 


>[!NOTE]
>
>These styles are a part of `layout.css` file, and you can edit them as required.

For example, you can use the color attribute in the `.inserted-block` style to define the way your inserted content appears in the published PDF output. 


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Similarly, you can use the `.deleted-block` style to define the way your deleted content appears in the published PDF output. 

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

You can use `.inserted-change-bar` and `.deleted-change-bar` style to modify the appearance of the change bars which appear on the left of the updated content.  

For example, you can use `-ro-change-bar-color` attribute in `.inserted-change-bar` style to show the inserted change bar in green color. You can also use `-ro-change-bar-color` attribute in `.deleted-change-bar` style to show the deleted change bar in red color. 

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt= "Changed bar topic content" width=500>

## Changed topic in the Table of Contents (TOC) 

You can also add a change bar on the left of the changed topics in the TOC of the PDF output. You can use `-ro-change-bar-color` attribute in the `.changed-topic` style to add a change bar in the color of your choice for the updated topics in the TOC list.  

For example, you can add a change bar of green color. 

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```
 

This shows a green change bar against all topics in the TOC where some updated have been done. You can click the changed topic in the TOC and view the detailed changes.

<img src="./assets/changed-bar-TOC.png" alt="Changed bar TOC" width=500>
