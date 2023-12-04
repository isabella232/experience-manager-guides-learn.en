---
title: Java-based API for creating and activating packages
description: Learn about the Java-based API for creating and activating packages
---
# Java-based API for creating and activating packages {#id175UB30E05Z}

The following Java-based API allows you to create and activate CRX packages. This API is available in the form of a bundle. You must include this bundle in your code to use this APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.3**

- Package: **com.adobe.fmdita.api.crxactivate**

- Class details:

    ```JAVA
    public class CRXActivator
    ```

    The **`CRXActivator`** class contains a method for creating CRX packages and replicating it on the publish instance.


## Create and activate packages 

The `activate` method creates a CRX package on the author instance and replicates it on the publish instance, if required. It is assumed that the AEM replication parameters have already been setup on the author instance. This method creates the CRX package based on a list of rules provided as input parameters in a JSON string.
>[!NOTE]
>
> Errors encountered during the creation or activation process are written to the `outputstream`.

**Syntax**:

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`json`|String|JSON string that determines the CRX package to be built. Use the following format to create the JSON string: <br>- `activate`: Is of type Boolean \(`true`/`false`\). Determines whether the CRX package created in the author instance is replicated to the publish instance. <br> - `rules`: Is of type JSON Array. An array of JSON rules which are processed sequentially to build the CRX package. <br> - `rootPath`: Is of type String. The base path upon which the node/property queries are executed. If no node/property queries are present, the root path and all nodes present under the root path are included in the CRX package. <br> - `nodeQueries`: Is of type Regex Array. An array of regular expressions used to include specific files under the root path. <br> - `propertyQueries`: Is of type JSON Array. An array of JSON Objects with each JSON Object consisting of an XPath query to be executed on the root path and the name of a property present in each JCR node after the query is executed. The value of the property in each JCR node should be a path or an array of paths. The paths present in this property are added to the CRX package.|
|`outputstream`|java.io.OutputStream|This is used to write the result of various stages, such as query execution, file inclusion, CRX package creation, or activation. Any error encountered during creation or activation process are written to the `outputstream`. This is useful for debugging.|
|`session`|String|A valid JCR session with activation permission.|

**Exception**:
Throws ``java.io.IOException``.

**Example**:
The following example shows how to build a JSON query:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

The example JSON query consists of the following rules:

-   Only the .png, .jpg, and .gif images under /content/dam/nested path are included in the package.
-   All node under /content/output/sites/hierarchy\_ditamap are included in the package.
-   The paths present in the `fileReference` property of nodes under /content/output/sites/hierarchy\_ditamap are included in the package.
