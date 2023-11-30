---
title: Java-based API to work with output generation
description: Learn about the Java-based API to work with output generation
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
---
# Java-based API to work with output generation {#id175UB30E05Z}

The following Java-based API allows you to generate output for a DITA map. This API is available in the form of a bundle. You must include this bundle in your code to use this APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.4**

- Package: ****com.adobe.fmdita.api.maps****

- Class details:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  The **`PublishUtils`** class contains a method for generating output for one or more output presets.


## Generate output 

The ``generateOutput`` method generates output for a DITA map file using the specified output presets.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|``sourcePath``|String|Path \(in the AEM repository\) of the DITA map file for which the output needs to be generated.|
|``outputName``|String|Name of the output preset\(s\) to be used to generate output. Multiple output presets can be specified using a pipe \("\|"\) delimiter, for example `aemsite\|pdfoutput`.|

**Exception**:
Throws ``javax.jcr.RepositoryException``, `java.io.IOException`, and `java.lang.Exception`.
