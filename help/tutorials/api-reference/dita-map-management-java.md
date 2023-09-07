# Java-based APIs to work with DITA maps {#id175UB30E05Z}

The following Java-based APIs allow you to work with DITA maps in AEM Guides. These APIs are available in the form of a bundle. You must include this bundle in your code to use these APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.2**

- Package: **com.adobe.fmdita.api.maps**

- Class details:

    ```JAVA
    public class **MapUtilities** extends Object
    ```

    The MapUtilities class contain methods for retrieving metadata information from a DITA map file.


## Download DITA map with dependents 

The `zipMapWithDependents` method creates a .zip file containing a DITA map along with all its dependents such as referenced topics, sub-maps, images, and DTDs. The .zip file for the DITA map is created based on a given baseline.

It also allows you to either maintain the same structure \(parent and child folders\) or create a flat file structure within a single folder for all dependent files.

>[!IMPORTANT]
>
> The API will throw an exception and fail to create a .zip file if any of the dependent files are missing.

**Syntax**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Path \(in the AEM repository\) of the DITA map file that needs to be downloaded.|
|`outputStream`|java.io.OutputStream|The stream to write the ZIP to.|
|`baseline`|String|The title of the baseline that is used to retrieve the versioned content. <br> **Note:** The value is case-sensitive.|
|flatFS|Boolean|\(Optional\) If set to true, then a flat structure of files is returned in the ZIP file. For example, if your DITA map refers to content in multiple folders, then all referenced files are pulled into a single folder. In case there are files with same name, then those files are renamed by adding a numeric suffix. All references \(in DITA map and topics\) are handled automatically, as they are updated based on the new location of files in the flat folder structure. If set to false, then the folder structure is maintained as is in the ZIP file. If the DITA map refers to files from multiple locations, then all those locations are also created in the ZIP file. When you restore the ZIP file, the exact folder structure is created at the destination location. <br> The default value for this parameter is false.|

**Returns**:
Contents of the ZIP are written to the `outputStream`.

**Exception**:
Throws ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Download DITA map with dependents \(Asynchronously\) 

Alternatively, you can download DITA map with dependents in an asynchronous mode. This approach is more useful for larger DITA maps.

The `zipMapWithDependents` method creates a .zip file containing a DITA map along with all its dependents such as referenced topics, sub-maps, images, and DTDs. The .zip file for the DITA map is created based on a given baseline.

It also allows you to either maintain the same structure \(parent and child folders\) or create a flat file structure within a single folder for all dependent files.

>[!NOTE]
>
> This node is auto deleted after some time based on output.history.purgetime configuration if defined, or 5 days as default.

**Syntax**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Path \(in the AEM repository\) of the DITA map file that needs to be downloaded.|
|`baseline`|String|The title of the baseline that is used to retrieve the versioned content. <br> **Note:** The value is case-sensitive.|
|flatFS|Boolean|\(Optional\) If set to true, then a flat structure of files is returned in the ZIP file. For example, if your DITA map refers to content in multiple folders, then all referenced files are pulled into a single folder. In case there are files with same name, then those files are renamed by adding a numeric suffix. All references \(in DITA map and topics\) are handled automatically, as they are updated based on the new location of files in the flat folder structure. If set to false, then the folder structure is maintained as is in the ZIP file. If the DITA map refers to files from multiple locations, then all those locations are also created in the ZIP file. When you restore the ZIP file, the exact folder structure is created at the destination location.<br>
The default value for this parameter is false.|

**Returns**:
The Node of the zip file is wrapped in the `CompletableFuture`class. The user can continue handling it asynchronously, and can use `.get()`method of the future to block the thread when the node is needed. The returned value can also end with an error, and that can be handled with `.exceptionally()` method.

## Get a list of baselines 

The ``getBaselineList`` method retrieves a list of all baselines that exist for a given DITA map.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Path \(in the AEM repository\) of the DITA map file for which the baseline information is to be retrieved.|

**Returns**:
A list of `HashMap` objects. Each `HashMap` object represents a baseline and contains the name and title of the baseline.

**Exception**:
Throws ``javax.jcr.RepositoryException``.

## Get a list of conditional presets 

The ``getConditionalPresetList`` method retrieves a list of all conditional presets that exist for a given DITA map.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Path \(in the AEM repository\) of the DITA map file for which the conditional preset information is to be retrieved.|

**Returns**:
A list of `HashMap` objects. Each `HashMap` object represents a conditional preset and contains the name and title of the conditional preset.

**Exception**:
Throws ``javax.jcr.RepositoryException``.

## Get the DITAVAL file information for a conditional preset 

The ``getDitavalFromConditionalPreset`` method retrieves the path of the DITAVAL file corresponding to a conditional preset for a given DITA map.

**Syntax**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Path \(in the AEM repository\) of the DITA map file for which the DITAVAL file is to be retrieved.|
|`cpName`|String|Name of the conditional preset in the DITA map for which the DITAVAL file is to be retrieved.|

**Returns**:
The path of the  DITAVAL file corresponding to the conditional preset defined in the DITA map file.

## Get all dependencies for a node 

The ``getAllDependencies`` method returns all dependencies of a given node.

**Syntax**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`rootNode`|javax.jcr.Node|The root node for which all dependencies are to be retrieved.|

**Returns**:
A node list containing all dependencies of the root node.

