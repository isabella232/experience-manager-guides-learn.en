---
title: Java-based APIs for conversion workflow
description: Learn about the Java-based APIs for conversion workflow
---
# Java-based APIs for conversion workflow {#id175UB30E05Z}

The following Java-based APIs allow you to convert HTML and Word documents into DITA format. These APIs are available in the form of a bundle. You must include this bundle in your code to use these APIs.

**Bundle details**:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.2**

- Package: **com.adobe.fmdita.api.conversion**

- Class details:

    ```JAVA
    public class ConversionUtils extends Object
    ```

    The **ConversionUtils** class contain methods for converting HTML and Word documents into DITA format.


## Convert HTML documents 

The `convertHtmlToDita` method converts HTML documents into DITA format.

**Syntax**:  

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`inputFile`|String|Absolute path of the source HTML files in AEM repository.|
|`destPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`createRev`|Boolean|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Exception**:
Throws `RepositoryException`.

## Convert Word documents 

The ``convertWordToDita`` method converts Word documents into DITA format.

**Syntax**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`inputFile`|String|Absolute path of the source Word files in AEM repository.|
|`destPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`style2tagMap`|String|Absolute path of the style mapping file that will be used for conversion.|
|`createRev`|Boolean|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Exception**:
Throws `RepositoryException`.
