---
title: Native PDF Publish Feature | Use JavaScript to work with content or style
description: Learn how to create use styleheets and create styles for your content.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
---
# Use JavaScript to work with content or style 

The Native PDF Publishing feature allows you to run JavaScript to manipulate your content or style applied on content before the final PDF is generated. This feature gives you complete control over how your final output is generated. For example, you may want to add legal notice information to the PDF output, which resides in another PDF. Using JavaScript, you can add the legal notice information once the PDF is created for the base content, but before the final PDF is generated.  
To support JavaScript execution, the Native PDF Publishing feature gives you the following callback functions:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: This callback function is executed before the TOC is generated. 
* `window.pdfLayout.onBeforePagination(callback)`: This callback function is executed after the TOC is generated, but before page breaks are added in the PDF.
* `window.pdfLayout.onAfterPagination(callback)`: This callback function is executed after the TOC and the page breaks are added in the PDF.

>[!NOTE]
>
>Internally, an execution sequence is maintained for these callout functions. First, onBeforeCreateTOC is executed, followed by onBeforePagination, and finally the  onAfterPagination is executed. 

Based on the type of content or style modification you want to perform, you can choose which callback function to use. For example, if you want to add content, then it is recommended to do it before the TOC is generated. Similarly, if you want to make some styling updates, then those can be done either before or after the pagination. 

In the following example, the position of the figure titles is changed from to above the images to below the images. For this, you need to enable the JavaScript execution option in the preset. To do this, perform the following steps:

1. Open the preset for editing.
1. Go to the **Advanced** tab.
1. Select the **Enable JavaScript** option. 
1. Save the preset and close. 

Next, create a JavaScript file with the following code and save it within the Resources folder of your template:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>The `window.addEventListener('DOMContentLoaded', function ()` function must be called before the callback functions are used. 

Next, this script has to be called from a template file that is used to generate the PDF output. For our example, we will add it in the TOC template. Ensure that the `<script>` tag is added within a predefined `<div>` tag inside the `<body>` tag. If you add it in the `<head>` tag or outside the `<body>` tag, the script will not execute. 

<img src="./assets/js-added-resources-template.png" width=500>

The output generated using this code, and the template displays the figure title below the image:

<img src="./assets/fig-title-below-image.png" width=500>

## Add a watermark to the PDF output for draft documents {#watermark-draft-document}

You can also use JavaScript to add conditional watermarks. These watermarks are added to your document when the defined condition is fulfilled.  
For example, you can create a JavaScript file with the following code to create a watermark to the PDF output of the document which is not yet approved. This watermark does not appear if you generate the PDF for the document in ‘Approved’ docstate. 

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

The PDF output generated using this code displays a watermark *Draft* on the cover page of your document:

<img src="./assets/draft-watermark.png" width=500>
