---
title: Native PDF Publish Feature | Use custom styles in footnotes
description: Learn how to apply style on the numbers in footnotes.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
---
# Apply footnote styles


Footnotes are notes placed at the bottom of a page that comment on or cite a reference for a designated part of the text. 

Every footnote has a footnote marker at the bottom of the page, which is generally a number or a symbol like an asterisk. Inside the main content, the same footnote marker appears as a footnote call and is indicated by the same number or symbol as a superscript. 




## Change the styles of footnote calls and markers

You can change the styles of the footnote calls and markers and manage their appearance in the PDF output. These styles help you quickly identify the footnotes in the document. 


**Example 1**:

Use the given example, to add a bracket before and after the footnote call and marker: 

* Add the prefix "(" and the suffix ")" using the content attribute in the `footnote-call` style, which will add the brackets around the footnote number in the topic content. 
* Add the prefix "(" and the suffix ")" using the content attribute in the `footnote-marker` style, which will add the brackets around the footnote number at the bottom of the page. 

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt= "Footer in PDF output" width=500 border="2px">

*Add brackets around the footnote call and the footnote marker.*

**Example 2**: 

You can also flag the footnote call and marker with an asterisk or lower Greek character instead of a number.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

In the output, you can view something like: 

<img src="./assets/footnote-number-2.png" alt= "Footer in PDF output" width=500 border="2px" >

*Add asterisk to a footnote call and marker.*

## Hide a footnote call

You can also apply a style to footnote calls with specific attributes. For example, use the following style to hide a footnote with the IDs: 
The footnote call is hidden in the main content, but the footnote marker appears at the bottom of the page.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Format the footnote area

The footnote area is where all footnotes are placed, generally at the bottom of a page. You can format the footnote area using the page layouts or CSS styles. 


### Page layouts

You can use the page properties for page layouts to style the footnote area in the different sections in a PDF document. For example, you can specify the margins and padding properties of the footnote area in a chapter. You can also change the border side, style, color, width, and radius. 

Learn about how to [work with the page properties of a page layout](./design-page-layout.md#page-props-page-layout). 

### CSS styles

 You can apply styles and format the footnote area in a PDF document. For example, you can change the border length, style, color, and width. 

 ```css
	@page {
	  @footnote {
    		border-top-style: solid;
    		border-top-color: #FF0000;
    		border-top-width: 3px;
  		        }
	      }

 ```

## Restart the numbering of footnotes

By default, the footnotes are numbered continuously in a document. However, you can use page layouts or CSS styles to restart the numbering of footnotes.


### Page layouts

You can specify a number in the page layouts to restart the footnote numbering in the different sections in a PDF document. For example, select a number from the **Restart numbering from** field in the Page Properties panel to restart the footnote numbering for each chapter.

### CSS styles

Use the following style to reset the footnote numbering on each page of the PDF output:

```css
@page
{
counter-reset: footnote
}
```

So, the footnotes on each page restart from 1.

## Display inline footnotes

Typically, each footnote appears as a block or begins on a new line. But you can also place them in line or next to each other.  

```css
.fn{
  	display: inline;
              }
```

## Apply styles to footnote cross-references

You can also cross-reference a footnote and refer to the same footnote multiple times in your PDF output. This helps you refer to the same citation or detailed note various times in the document without creating a footnote for it again.

For example, the following screenshot shows how the same footnote is cross-referenced to all cities in the PDF output.
<img width="550" alt="footnote references in a pdf" src="./assets/link-footnotes.png" border="2px"> 

*Insert the cross-reference to a footnote.*





Using CSS styles, you can also format the cross-references to footnotes. For example, you can change the background color of the cross-references.

```css
    .xref-fn{
	background-color: red;
	}
```



