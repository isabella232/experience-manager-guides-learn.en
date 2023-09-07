# Java-based APIs to work with baseline and labels {#id175UB30E05Z}

The following Java-based APIs allow you to create baseline and add labels to files in a baseline. These APIs are available in the form of a bundle. You must include this bundle in your code to use these APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.5**

- Package: ****com.adobe.fmdita.api.baselines****

- Class details:

  ```JAVA
  public class **BaselineUtils** extends Object
  ```

  The ****BaselineUtils**** class contain methods for creating baselines and applying labels to files in a baseline.


## Create a baseline 

The create baseline`` method has two versions – one for XML Documentation solution version 3.5, and other for versions prior to 3.5 release \(which includes versions 3.4, 3.3, and 3.2\). The version 3.5 API allows creation of baseline using a label, direct references, and indirect references in a map file.

The other version of API uses the date and time to create a baseline. This API is retained for backward-compatibility with systems using XML Documentation solution 3.4, 3.3, or 3.2.

**Syntax \(for version 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session. The user session needs to have both read and write permissions for the DITA map and read permission for all the reference files included in the baseline.|
|`sourcePath`|String|Absolute path of the DITA map file in AEM repository.|
|`baselineTitle`|String|A unique title for the baseline.|
|`label`|String|Select the version of a topic that has the given label applied on it.|
|`directContext`|LinkedHashMap<String, Object\>|The configurations on the basis of which directly referenced topic \(content\) is selected, the order mentioned in the map is followed to resolve a version. <br> If after iteration on all keys of the map, no version is found, then the baseline creation process fails. <br> If the HashMap is empty \(send empty and not null map for default\), then by default it, is populated as: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> If you want the baseline creation to only pick version of a given label and fail if no such version exists, then put the `label` key and the label you want to create baseline on.|
|`indirectContext`|LinkedHashMap<String, Object\>|The configurations on the basis of which indirectly referenced topic \(referenced content\) is selected, the order mentioned in the map is followed to resolve a version. <br> If after iteration on all keys of the map, no version is found, then the baseline creation process fails. <br> If the HashMap is empty \(send empty and not null map for default\), then by default, it is populated as: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> If you want it to be the latest version in place of picking up a version automatically, then replace: <br>`indirectContext.put("pickAutomatically", null);` <br> _with:_ <br>`indirectContext.put("latest", true)`|

**Returns**:
The name of the baseline, which is the node name of the baseline in the JCR repository. The title of the newly created baseline will be shown to the user on the Baseline page for the DITA map.

**Exception**:
Throws ``ItemExistExceptiom`` if a baseline with the same title already exists.

**Syntax \(for versions 3.4, 3.3, and 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session. The user session needs to have both read and write permissions for the DITA map and read permission for all the reference files included in the baseline.|
|``sourcePath``|String|Absolute path of the DITA map file in AEM repository.|
|`baselineTitle`|String|A unique title for the baseline.|
|`versionDate`|Date|The baseline is created using the versions of topics\(directly referenced from the DITA map\) as on this date. Specify the date in `d-MM-yyyy H:mm` format.|

**Returns**:
The name of the baseline, which is the node name of the baseline in the JCR repository. The title of the newly created baseline will be shown to the user on the Baseline page for the DITA map.

**Exception**:
Throws ``RepositoryException.``

## Apply labels 

The ``applyLabel`` method applies one or multiple labels to the files in a baseline.

**Syntax**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Absolute path of the DITA map file in AEM repository.|
|``baselineName``|String|Name of the baseline node on which the label has to be applied. To get the name of the baseline node, you can use the [\#id185NFF0085Z](#id185NFF0085Z) method or check the baselines node of the DITA map in CRXDE.<br> **Note:** Label is applied to version of files that are directly referenced from the map file in the baseline.|
|`label`|String|A label that is applied on files in the baseline. Ensure that the label does not contain the following characters:
`/,:,\[,\],\|,\*` <br> In case you want to set multiple labels, then separate labels with a comma; for example Label1, Label2.|

**Exception**:
Throws `RepositoryException`.

## Delete labels 

The ``deleteLabel`` method deletes one or multiple labels from the files in a baseline.

**Syntax**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`sourcePath`|String|Absolute path of the DITA map file in AEM repository.|
|`baselineName`|String|Name of the baseline from which the label has to be deleted. <br> **Note:** Label is deleted from the version of files that are directly referenced from the map file in the baseline.|
|`label`|String|A label that is to be deleted from files in the baseline. <br> In case you want to delete multiple labels, then separate labels with a comma; for example Label1, Label2.|

**Returns**:
The map with *key:value* pair of `path:deletedlabels` for all files in the baseline.

**Exception**:
Throws ``RepositoryException`, `VersionException`, `Exception``.

