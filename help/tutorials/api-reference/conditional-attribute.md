---
title: REST API to work with conditional attributes
description: Learn about the REST API to work with conditional attributes
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
---
# REST API to work with conditional attributes {#id175UB30E05Z}

The following REST API allows you to add conditional attributes in a folder profile.

## Add conditional attribute in a folder-level profile 

A POST method that adds conditional attributes to a given folder-level profile.

**Request URL**:   
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/folderprofiles

**Parameters**:   
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is ``ADDATTRIBUTEPROFILES``. <br> **Note:** The value is case-insensitive.|
|`profilename`|String|Yes|Display name of the folder-level profile in which the conditional attributes have to be added.|
|`conditionalprofiles`|JSON array|Yes|A JSON array consisting of the conditional attribute name and values. The following example code snippet shows the JSON array with two attributes - `platform` and `product` with multiple values assigned to them.| 

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
``` 

**Response values**:   
Returns a HTTP 200 \(Successful\) response.
