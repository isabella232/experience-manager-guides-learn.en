---
title: REST APIs for Output management
description: Learn about REST APIs for Output management
---

# REST APIs for Output management {#id175UB30E05Z}

The following REST APIs are available for managing output in AEM Guides.

## Get all output presets for a DITA map 

A POST method that retrieves all output presets configured for a DITA map.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:   
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is `getalloutputs`.<br> **Note:** The value is case-insensitive.|
|`sourcePath`|String|Yes|Absolute path of the DITA map file.|

**Response values**:
Returns an array of JSON Output Preset objects, each object containing the following elements:

|Element|Description|
|-------|-----------|
|`outputName`|Name of the output preset. Output names are unique in the scope of the DITA map they are defined in.|
|`outputType`|Type of output generated using this preset, for example AEM Site, PDF, EPUB or other. The available options are:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   CUSTOM|
|`outputTitle`|A descriptive name for the output preset settings. This is used to define the value for the Setting Name property for the output preset.|
|`ditaValPathList`|Array of DITAVAL file paths to be used to generate the desired output.|
|`targetPath`|Path where the output is published or stored.|
|`siteName`|*\(For AEM Site output\)* Name of the AEM Site.|
|`templatePath`|*\(For AEM Site output\)* Path of the template node to be used to generate the desired output.|
|`searchScope`|Specify the scope for the search operation. The value for this parameter must be set to `local`.|
|`generateTOC`|*\(For AEM Site output\)* Specify whether a TOC is generated \(true\) or not \(false\).|
|`generateBreadcrumbs`|*\(For AEM Site output\)* Specify whether the breadcrumbs are generated \(true\) or not \(false\).|
|`overwriteStrategy`|*\(For AEM Site output\)* Specify whether files at the destination are overwritten \(true\) or not \(false\).|
|`pdfGenerator`|Specify the PDF generation engine to use. The possible values are:<br>-   DITAOT <br>-   FMPS|

>[!NOTE]
>
> `DitaValPath` element is no longer supported.

## Create output preset 

A POST method that creates a new output preset for a DITA map.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is ``createoutput``.<br> **Note:** The value is case-insensitive.|
|`sourcePath`|String|Yes|Absolute path of the DITA map file.|
|`outputTitle`|String|Yes|A descriptive name for the output preset settings. This is used to define the value for the Setting Name property for the output preset.<br> **Note:** When a new output preset is created, the back-end system drives a unique name for the output preset from the given title.|
|`outputType`|String|Yes|Type of output generated using this preset, for example AEM Site, PDF, EPUB or other. The available options are:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   CUSTOM|

**Response values**:
|Element|Description|
|-------|-----------|
|`outputName`|A unique name for the newly created output preset. This name is derived from the value of the `outputTitle` parameter.|

## Save output preset 

A POST method that saves changes made in an output preset.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is ``saveoutput``.<br> **Note:** The value is case-insensitive.|
|`sourcePath`|String|Yes|Absolute path of the DITA map file.|
|`outputObj`|String|Yes|A JSON object that contains properties of the output preset that is being updated. The `outputObj.outputName` property contains the name of the output preset that is to be updated. For the format of the JSON object, see the [Response values](#id177BC0I0L5Z) table in *Get all output presets for a DITA map*.|

**Response values**:
Returns a HTTP 200 \(Successful\) response.

## Get a specific output preset 

A POST method that retrieves an existing output preset.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is `getoutput`. <br>**Note:** The value is case-insensitive.|
|`sourcePath`|String|Yes|Absolute path of the DITA map file.|
|`outputName`|String|Yes|Name of the output preset for which the details have to be retrieved.|

**Response values**:
|Element|Description|
|-------|-----------|
|`outputName`|Name of the output preset. Output names are unique in the scope of the DITA map they are defined in.|
|`outputType`|Type of output generated using this preset, for example AEM Site, PDF, EPUB or other. The available options are:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   CUSTOM <br>|
|`outputTitle`|A descriptive name for the output preset settings. This is used to define the value for the Setting Name property for the output preset.|
|`ditaValPathList`|Array of DITAVAL file paths to be used to generate the desired output.|
|`targetPath`|Path where the output is published or stored.|
|`siteName`|\(For AEM Site output\) Name of the AEM Site.|
|`siteTitle`|\(For AEM Site output\) Title of the AEM Site.|
|`templatePath`|\(For AEM Site output\) Path of the template node to be used to generate the desired output.|
|`searchScope`|Specify the scope for the search operation. The value for this parameter must be set to `local`.|
|`generateTOC`|\(For AEM Site output\) Specify whether a TOC is generated \(true\) or not \(false\).|
|`generateBreadcrumbs`|\(For AEM Site output\) Specify whether the breadcrumbs are generated \(true\) or not \(false\).|
|`overwriteFiles`|\(For AEM Site output\) Specify whether files at the destination are overwritten \(true\) or not \(false\).|
|`pdfGenerator`|Specify the PDF generation engine to use. The possible values are:<br>-   DITAOT <br>-   FMPS|

>[!NOTE]
>
> `DitaValPath` element is no longer supported.

## Generate output 

A GET method that generates output using one or more output presets.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`operation`|String|Yes|Name of the operation being called. The value of this parameter is `GENERATEOUTPUT`.<br> **Note:** The value is case-sensitive.|
|`source`|String|Yes|Absolute path of the DITA map file.|
|`outputName`|String|Yes|Name of the output preset\(s\) to be used to generate output. Multiple output presets can be specified using a pipe \("\|"\) delimiter, for example `aemsite|pdfoutput`.|

**Response values**:
Returns a HTTP 200 \(Successful\) response.

## Generate incremental output 

A GET method that generates incremental output for an AEM Site using one or more output presets.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`operation`|String|Yes|Name of the operation being called. The value of this parameter is `INCREMENTALPUBLISH`. <br>**Note:** The value is case-sensitive.|
|`contentPath`|JSON|Yes|Absolute path of the DITA map file and topic files along with the name of output presets. Use the following example as the building block:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- The `ditamap` attribute takes the absolute path of the DITA map that is used to generate the output. 
- The `topics` attribute takes an array of topics that are updated and need to be republished.
- The `fullMaps` attribute contains path of the map files \(like chunked submaps\) that are needed along with their topics for incremental output generation. 
- The `maps` attribute contains path of the map files \(for resolving keyspace references\) that are extracted on the disk without topics. 
- The `outputs` attribute takes an array of output preset names that are used to generate the output.

**Response values**:
Returns a HTTP 200 \(Successful\) response.

## Delete output preset 

A POST method that deletes an output preset.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/publishlistener

**Parameters**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is `deleteoutput`.<br> **Note:** The value is case-insensitive.|
|`sourcePath`|String|Yes|Absolute path of the DITA map file.|
|`outputName`|String|Yes|Name of the output preset to delete.|

**Response values**:
Returns a HTTP 200 \(Successful\) response.

