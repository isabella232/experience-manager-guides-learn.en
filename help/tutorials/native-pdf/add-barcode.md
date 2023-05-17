---
title: Native PDF Publish Feature | Add barcode
description: Learn how to add barcodes.
---
# Add a barcode to the PDF output

Barcodes can be useful to include information that can be easily processed by machines. Similarly, QR codes can be used for the links that readers can open with their mobile devices. 


This tutorial helps you to add barcodes on the top of every page in the PDF output. 

## Steps to generate a barcode

To generate the barcode, perform the following steps: 


### Add the resource ID to the DITA map

Add the resource ID element to the DITA map and use it as the content to generate the barcode. 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```

You can also edit this ID in the authoring mode. 

<img src="./assets/barcode-map.png" alt="Sample output with barcode" width=700>


### Add a barcode placeholder to the template header

Modify the `Common.plt` file in the **Basic** template to add a barcode after the project title.  

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### Update the template CSS to render a barcode value

Modify the `content.css` file to render a barcode during the PDF generation. Various barcode types like 'qrcode' and 'pdf417' are available.  For more details, see [Barcode types](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

Once you have performed the previous steps, you can generate the PDF output with a barcode. 

The following screenshot displays a sample barcode in a PDF output.

<img src="./assets/barcode-output-sample.png" alt="Sample output with barcode" width=700>


## Barcode types {#barcode-types}

| Type                            | CSS attribute           | Additional attribute(s)    |
| ------------------------------- | ----------------------- | -------------------------- |
| QR Code                         | qrcode                  |                            | 
| PDF417                          | pdf417                  |                            |
| DataMatrix                      | data-matrix             |                            |
| Aztec Code                      | aztec-code              |                            |
| Grid Matrix                     | grid-matrix             |                            |
| Maxicode                        | maxicode mode-4         |                            |
| Micro QR                        | microqr                 |                            |
| Code One                        | code-one                |                            |
| Codablock F                     | codablockf              |                            |
| GS1 Databar Limited             | databar-limited         |                            |
| GS1 Databar Omnidirectional     | databar omnidirectional |                            |
| EAN-13                          | ean-13                  |                            | 
| GS1-128 (EAN-128)               | code128                 | -ro-barcode-encoding: gs1; | 
| ITF-14                          | itf14                   |                            | 
| UPC-A                           | upc-a                   |                            | 
| Code 128                        | code128                 |                            | 
| Interleaved 2 of 5              | code2of5 interleaved    |                            | 
| POSTNET                         | postnet                 |                            | 
| Dutch Post Kixcode              | kixcode                 |                            | 
| Korea Post                      | korea-post              |                            | 
| Deutsche Post Leitcode          | dp-leitcode             |                            | 
| Australia Post                  | auspost                 |                            | 
| Logmars                         | logmars                 |                            | 
| Pharmacode                      | pharmacode              |                            | 
| USPS OneCode (Intelligent Mail) | usps-onecode            |                            | 


