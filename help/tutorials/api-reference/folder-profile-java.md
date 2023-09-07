---
title: Java-based API to work with folder profiles
description: Learn about the Java-based API to work with folder profiles 
---

# Java-based API to work with folder profiles {#id175UB30E05Z}

The following Java-based API allows you to add conditional attributes to a folder-level profile. This API is available in the form of a bundle. You must include this bundle in your code to use this APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.2**

- Package: **com.adobe.fmdita.api.profiles**

- Class details:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  The **`FolderProfileUtils`** class contains a method for adding conditional attributes in a folder profile.


## Add conditional attributes to a folder profile 

The ``addAttributeProfiles`` method adds conditional attributes to a folder-level profile.

**Syntax**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|``attributeNames``|String|A list of attribute names.|
|``values``|String|A list of values for the given attributes.|
|`labels`|String|A list of labels for the `attribute`- `value` pairs. [1](#fntarg_1)|
|`profileName`|String|The name of the folder-level profile to which these attributes, values, and labels have to be applied. **Important:** All existing attributes-values-labels defined in the profile are overwritten.|
|`session`|javax.jcr.Session|A valid JCR session.|

**Returns**:
`true` for success. In case of a failure, it throws an exception.

**Exception**:
Throws ``java.lang.Exception`` in the following scenarios:

- If the API couldn't get `resourceResolverFactory` object. In that case, you should restart the bundle.
- If parameters passed to the API are invalid.
- If the API is called through unauthorized user session, such as the user who is not an administrator for the given folder profile.

[1](#fnsrc_1) The `attributeNames`, `values`, and `labels` at the same index in an array list must correspond to the same entry.

