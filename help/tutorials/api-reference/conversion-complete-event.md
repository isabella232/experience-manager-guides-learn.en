# Conversion process event handler {#id175UB30E05Z}

AEM Guides exposes com/adobe/fmdita/conversion/complete event that is used to perform any post-processing operations after completion of a document conversion process. This event is triggered whenever an non-DITA document is migrated into DITA file format. For example, if you run a Word to DITA conversion or InDesign to DITA conversion process, this event is called after the conversion process ends.

You need to create an AEM event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameters**:   
|Name|Type|Description|
|----|----|-----------|
|`status`|String|The return status for the operation performed. The possible options are: -   SUCCESS: The conversion process completed successfully. <br> -   COMPLETED WITH ERRORS: The conversion process completed, but with some errors. <br>-   FAILED: The conversion process failed due to some fatal error.|
|`filePath`|String|Absolute path of the source file \(to be converted\) in AEM repository.|
|`outputPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`logPath`|String|Absolute path of the node where the conversion log will be saved.|

