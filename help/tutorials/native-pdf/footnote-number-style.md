---
title: Native PDF Publish Feature | Use custom styles in footnotes
description: Learn how to apply style on the numbers in footnotes.
---
# Use custom styles in footnotes

Footnotes are notes placed at the bottom of a page that comments on or cites a reference for a designated part of the text. 

You can style the numbers in the footnote call present in the topic content and the footnote marker present at the bottom of the page. For example, you can add brackets around the number or change their color. These styles help you easily identify the footnotes in the document. 

```css
...
.footnote::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.footnote::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```

In the given example, a bracket is added before and after the footnote call and marker: 

* Add the prefix "(" and the suffix ")" using the content attribute in the `footnote-call` style which will add the brackets around the footnote number in the topic content. 
* Add the prefix "(" and the suffix ")" using the content attribute in the `footnote-marker` style which will add the brackets around the footnote number at the bottom of the page. 

<img src="./assets/pdf-output-footer-numbers.png" alt= "Footer in PDF output" width=500>
