---
title: Configure search for AEM Assets UI
description: Learn how to Configure search for AEM Assets UI
exl-id: a5567db7-34ad-48d5-909d-78a5ee45f0a9
---
# Configure search for AEM Assets UI {#id192SC800MY4}

By default, AEM does not recognize DITA content, thus, it doesn't provide any mechanism to search DITA content within its repository. AEM Guides allows you to add the DITA content search capability in AEM repository.

By default, AEM does not recognize DITA content, thus, it doesn't provide any mechanism to search DITA content within its repository. Also, there's no OOTB capability to search content based on their UUID. AEM Guides allows you to add the DITA content search and UUID-based search capabilities in the AEM repository.

Configuring DITA content search involves the following tasks:

1.  [Add DITA Element search component in Assets UI](#id192SF0F50HS)
1.  [Add UUID-based search component in Assets UI](#id2034F04K05Z)
1.  [Provide permissions to users](#id192SF0G0RUI)
1.  [Add custom elements or attributes in search](#id192SF0G10YK)
1.  [Extract metadata from existing content](#id192SF0GA0HT)

In addition to adding search capability, you can also configure the folders that should not be included in the search. For more details, see [Exclude temporary files from search results](#id197AHI0035Z).

## Add DITA Element search component in Assets UI {#id192SF0F50HS}

Perform the following to add DITA content search component in AEM Assets UI:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the **Adobe Experience Manager** link at the top and choose **Tools**.

1.  Select **General** from the list of tools and click on the **Search Forms** tile.

1.  In the **Search Forms** list, select the **Assets Admin Search Rail**.

1.  Click **Edit**.
1.  In the **Select Predicate** tab, scroll to the end of the list.

1.  Drag-and-drop **DITA Element Predicate** at the required location in the search form.

    ![](assets/drag-search-predicate.png){width="650" align="left"}

1.  Click **Done** to save your changes.

    When you access the Filters option in the Assets UI, you will get the DITA Element search filtering option.

    ![](assets/search-filter-asset-console.png){width="350" align="left"}


## Add UUID-based search component in Assets UI {#id2034F04K05Z}

Perform the following to add UUID-based search component in AEM Assets UI:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the **Adobe Experience Manager** link at the top and choose **Tools**.

1.  Select **General** from the list of tools and click on the **Search Forms** tile.

1.  In the **Search Forms** list, select the **Assets Admin Search Rail**.

1.  Click **Edit**.
1.  In the **Select Predicate** tab, choose **Property Predicate** and drag-and-drop it at the required location in the search form.

1.  In the **Settings** tab, provide the following details for the newly added **Property Predicate** component:

    -   **Field Label**: UUID
    -   **Property Name**: jcr:content/fmUuid
1.  Click **Done** to save your changes.

    When you access the Filters option in the Assets UI, you will get the UUIS-based search filtering option.


## Provide permissions to users {#id192SF0G0RUI}

The Authors and Publishers would need to be given explicit permissions to be able to access the search capabilities from Assets UI. If you do not grant these permissions, then your users will not be able to search DITA content based on their element/attribute values or UUID.

Perform the following steps to provide access to the DITA Search feature:

1.  Access the user and group permissions page. The default URL to access the page is:

    `http://<server name>:<port>/useradmin.html`

1.  Search for the user group or an individual user to whom you want to give access. For example, to give access to all users in authors group, enter authors in the **Filter Query** field and press **Enter**.

    ![](assets/authors-group-permission.png){width="350" align="left"}

1.  Select the **authors** group.

1.  In the right pane, select the **Permissions** tab.

1.  Navigate to the following folder location:

    /conf/global/settings/dam/search

1.  Give the **Read** permission on the search folder.

    ![](assets/read-permission-authors.png){width="650" align="left"}

1.  Click **Save**.


The selected user or user group will now have access to the search DITA content feature in the Assets UI.

## Add custom elements or attributes in search {#id192SF0G10YK}

For the DITA search to work, some preprocessing of the DITA content is required. This preprocessing step extracts selective content from individual DITA maps and topics so that it can be indexed for faster searching. Internally, this process is called *Serialization*. Serialization of DITA files takes place during content upload or can also be executed on-demand. It uses a configuration file to determine how much content from each DITA file should be indexed. The default location of the serialization file is:

/libs/fmdita/config/serializationconfig.xml

The default search configuration allows you to search for all elements and attributes within the DITA `prolog` element. If you want to search on the basis of other elements or attributes, then you need to configure the search serialization file.

>[!NOTE]
>
> If you want to go with the default search configuration within the `prolog` element, then you can skip this process.

This file contains two main sections—attribute set and rule set. A snippet of the rule set section is given below:

```XML
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

In the rule set section, you can specify:

-   Rules to extract the elements

-   Rules to extract attributes


A rule consists of the following:

xpath
:   This is the XPath query that retrieves the elements or attributes from DITA files. The default configuration for the element rule retrieves all `prolog` elements. And, the default configuration for the attribute rule retrieves all attributes of `prolog` elements. You can specify an XPath query to serialize the elements or attributes that you want to search for.

    The XPath query contains the class name of the document type. The `topic/topic` class is used for topic type DITA documents. If you want to create a rule for other DITA documents, then you must use the following class names:

    |Document Type|Class name|
    |-------------|----------|
    |Topic|- topic/topic|
    |Task|- topic/topic task/task|
    |Concept|- topic/topic concept/concept|
    |Reference|- topic/topic reference/reference|
    |Map|- map/map|

text
:   If you want to search for the text within the specified element, then specify the yes value. If you specify no as value, then only the attributes within the element are serialized. The attributes that you want to search for need to be specified in the attribute set section.

attributeset
:   Specify the ID of the attribute set that you want to associate with this rule. The value all-attrs is a special case to indicate that all attributes for this rule must be serialized.

An attribute set contains a list of attributes that you want to search for within DITA content. The attribute set contains the following:

id
:   A unique identifier for the attribute set. This id is specified in the attributeset parameter of a rule set.

attribute
:   A list of attributes that you want to search. For each attribute, you need to create an individual entry in the `attribute` element.

Perform the following steps to add custom DITA elements or attributes in the search serialization file:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the serialization configuration file available at the following location:

    /libs/fmdita/config/serializationconfig.xml

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/serializationconfig.xml`

1.  Add the required element or attribute rule sets.

1.  Save the file.

1.  Open the Adobe Experience Manager Web Console Configuration page. The default URL to access the configuration page is:

    http://<server name\>:<port\>/system/console/configMgr

1.  Search for and click on the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Click **Save**.


The new serialization information is stored and activated for search. However, you must extract the metadata from your existing DITA content to become available for search.

## Extract metadata from existing content {#id192SF0GA0HT}

Once you have made any change in the default search serialization file, you must enable the DITA Metadata Extraction option in the *com.adobe.fmdita.config.ConfigManager* bundle and then run the workflow to extract metadata. This extracts the required metadata from the existing DITA files and the same is then made available for search.

In case you create new files or edit any file after updating the serialization file, then the metadata is automatically extracted from such files. The process of extracting metadata is only required for files that already exist in the AEM repository.

Extracting metadata from existing DITA files involves two tasks:

1.  Enabling the metadata extraction option in the configMgr
1.  Running the metadata extraction workflow

Perform the following steps to enable the metadata extraction option in the configMgr:

1.  Open the Adobe Experience Manager Web Console Configuration page. The default URL to access the configuration page is:

    http://<server name\>:<port\>/system/console/configMgr

1.  Search for and click on the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Select the **Enable DITA Metadata Extraction** option.

1.  Click **Save**.


Perform the following steps to run the metadata extraction workflow:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the **Adobe Experience Manager** link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools and click the **DITA Metadata Extraction** tile.

1.  If you want to extract metadata from a single file and its dependencies, click the **Select a File** link and browse for a file.

1.  If you want to extract metadata from multiple files within a folder, click the **Select Folder\(s\)** link, browse and select the required folder. Click the **Add** button to add the folder to the serialization task list.

    >[!NOTE]
    >
    > You can select and add multiple folders to a serialization task.

1.  Click **Start**.

1.  In the Confirm Metadata Extraction dialog, click **OK**.


## Exclude temporary files from search results {#id197AHI0035Z}

By default, the search is performed on the entire repository of AEM. There could be some locations that you would like to exclude from search. For example, when you initiate the content translation workflow, the unapproved files remain in a temporary folder location. When you perform the search, files from this temporary location are also returned in the search results.

To prevent AEM Guides from searching the temporary translation folder location, you need to add temporary folder location in the exclude list.

Perform the following steps to exclude the temporary translation folder from the search:

>[!NOTE]
>
> You can add any other folder location to the exclude list using this procedure.

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the damAssetLucene node available at the following location:

    /oak:index/damAssetLucene

1.  Add the following property in the damAssetLucene node:

    |Property name|Type|Value|
    |-------------|----|-----|
    |excludedPaths|String\[\]|Add the following value to this property: <br>/content/dam/projects/translation\_output|

1.  Navigate to the lucene node available at the following location:

    /oak:index/lucene

1.  Add the following property in the lucene node:

    |Property name|Type|Value|
    |-------------|----|-----|
    |excludedPaths|String\[\]|Add the following values to this property: <br><ul><li>/var/dxml</li><li>/content/dam/projects/translation\_output</li></ul> |
