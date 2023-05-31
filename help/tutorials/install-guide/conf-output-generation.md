---
title: Configure output generation settings
description: Learn how to Configure output generation settings
exl-id: 95e8be72-2bba-42c8-8095-5f7f9bedb46f
---
# Configure output generation settings {#id181AI0B0E30}

AEM Guides comes with a lot of configuration options for you to customize the output generation process. This topic covers all configurations and customizations that would help you set up your output generation process.

## Configure the Baseline tab on the DITA map dashboard {#id223MD0D0YRM}

You can configure and hide the Baseline tab available on map dashboard.

The **Hide Baseline Tab** option is not enabled by default and you need to enable this from the configMgr. Perform the following steps to enable the option by default in the Web Editor:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Hide Baseline Tab** option.

1.  Click **Save**.

    >[!NOTE]
    >
    > This configuration is disabled by default and the Baseline tab is available on the map dashboard.


## Configure FrameMaker Publishing Server {#id1678G0Z0TN6}

You can use FrameMaker Publishing Server \(FMPS\) to generate output for your DITA content. Configuring FMPS will allow you to generate output in multiple formats supported by FMPS.

>[!NOTE]
>
> To generate output using FMPS, you need to have the FMPS server setup. For installation and configuration details, see the FrameMaker Publishing Server User Guide.

To configure AEM Guides to use FMPS, update the following properties of the `com.adobe.fmdita.config.ConfigManager` bundle in the Web Console.

>[!NOTE]
>
> Access http://<server name\>:<port\>/system/console/configMgr URL to open the Web Console.

|Property|Description|
|--------|-----------|
|FrameMaker Publishing Server Login Domain|Specify the domain name or the workgroup name on which the FrameMaker Publishing Server is hosted. Based on the FMPS version, provide the domain name as:-   **FMPS 2020**: IP address as 192.168.1.101 <br>- **FMPS 2019 and earlier**: IP address or the domain name|
|FrameMaker Publishing Server URL|Specify the URL of the FrameMaker Publishing Server. Based on the FMPS version, provide the FMPS URL as:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 and earlier**: `http://<fmps_ip>:<port>/fmserver/v1/`|
|FMPS Version|Specify the version number of the FrameMaker Publishing Server. Based on the FMPS version, provide the version information as: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 and earlier**: 2019 or 2017|
|FrameMaker Publishing Server Username and Password|Specify the user name and password to access the FrameMaker Publishing Server.|
|FMPS Timeout|\(*Optional*\) Specify the time \(in seconds\) for which AEM Guides waits for a response from the FrameMaker Publishing Server. If no response if received in the specified time, AEM Guides terminates the publishing task and the task is flagged as failed. <br> Default value: 300 seconds \(5 minutes\)|
|External AEM URL|*\(Optional\)* The AEM URL where the FrameMaker Publishing Server will place the generated output files. For example, `http://<server-name>:<port>/`.|
|AEM Admin Username and Password|*\(Optional\)* The user name and password for an administrator of your AEM setup. This will be used by FrameMaker Publishing Server to communicate with AEM.|
|FMPS Task Execution Wait Timeout|This setting is applicable only for FMPS 2020. Specify the time \(in seconds\) after which FMPS will stop waiting for this process to execute.|

## Configure blended publishing within an existing AEM Site {#id1691I0V0MGR}

If you have an AEM Site that contains DITA content, you can configure your AEM Site output to publish DITA content to a predefined location within your site. For example, in the following screenshot of an AEM Site page, the `ditacontent` node is reserved to store DITA content:

![](assets/publish-in-aem-site.png){width="300" align="left"}

The remaining nodes in the page are authored directly from the AEM Site editor. Configuring the publish setting to publish DITA content to a predefined location ensures that none of your existing non-DITA content gets modified by the AEM Guides publishing process.

You need to perform the following configurations on your existing site to allow publishing of DITA content to a predefined node:

-   Configure your site's template properties

-   Add nodes in your site to publish DITA content


Perform the following steps to configure your existing site's template properties:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to your site's template configuration node. For example, AEM Guides stores the default template configurations in the following node:

    `/libs/fmdita/config/templates/default`

    >[!NOTE]
    >
    > Do not make any customizations in the default configuration files available in the `libs` node. You must create an overlay of the `libs` node in the `apps` node and update the required files in the `apps` node only.

1.  Add the following properties:

    |Property name|Type|Value|
    |-------------|----|-----|
    |`topicContentNode`|String|Specify the node name where you would like to publish the DITA content. For example, the default node where AEM Guides publishes DITA content is: <br>`jcr:content/contentnode`|
    |`topicHeadNode`|String|Specify the node name where you would like to store the metadata information of your DITA content. For example, the default node where AEM Guides stores metadata information is: <br>`jcr:content/headnode`|


The following screenshot shows the properties added in the default template node of AEM Guides:

![](assets/add-content-node.png){width="800" align="left"}

Next time when you publish any DITA content using your site's template configurations, the content gets published into the nodes specified in the `topicContentNode` and `topicHeadNode` properties.

However, for existing sites, you must manually add the `topicContentNode` and `topicHeadNode` nodes.

Perform the following steps to add the required nodes to your existing site:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Locate `jcr:content` within your site node.

1.  Add `topicContentNode` and `topicHeadNode` nodes with the same name that you specified in the site's template configurations.


## Customize AEM Site output {#id166TG0B30WR}

AEM Guides supports creating outputs in following formats:

-   AEM Site

-   PDF

-   HTML5
-   EPUB
-   Custom output through DITA-OT

For the AEM Site output, you can assign different design templates with different output tasks. These design templates can render the DITA content in different layouts. For example, you could specify different design templates for internal and external audiences.

You can also use customized DITA Open Toolkit \(DITA-OT\) plug-ins with AEM Guides. You can upload these custom DITA-OT plug-ins to generate PDF output in a specific way.

>[!TIP]
>
> See the *AEM Site publishing* section in the Best practices guide[appendix.md\#](appendix.md#) for best practices around creating AEM Site output.

### Customize design template for generating output {#customize_xml-add-on}

AEM Guides uses a set of predefined design templates to generate AEM Site output. You can customize the AEM Guides' design templates to generate the output that conforms to your corporate branding. A design template is a collection of various styles \(CSS\), scripts \(both server- and client-side\), resources \(images, logos, and other assets\), and JCR nodes that tie all these resources together. A design template can be as simple as a single server-side script with just a couple of JCR nodes, or a complex combination of styles, resources, and JCR nodes. Design templates are used by AEM Guides publishing subsystem while generating AEM Site output and they control the structure, look and feel of the generated output.

There is no restriction as to where the design template resources should be located on the server, but they are usually logically organized as per their function. For example, the default template has all its JavaScript and CSS files stored under `/etc/designs/fmdita/clientlibs/siteoutput/default` folder. Wherever these files are located, they are linked together by a collection of JCR nodes. Together, these JCR nodes and the files constitute the whole design template.

The default design template shipped with AEM Guides allows you to customize the landing, topic, and search page components. You can make a copy of the default design and the corresponding reference templates and specify different components to generate the desired output.

Perform the following steps to specify your own design template to use for AEM Site output generation:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default design template node. The location of the default design template node is:

    `/libs/fmdita/config/templates/`

    ![](assets/templates-node.png){width="300" align="left"}

    >[!NOTE]
    >
    > Make a copy of the default design templates from the `libs` folder to the `apps` folder and make changes in the `apps` folder. You must also make changes in the templates referenced from the default template node. The referenced templates are placed under `/libs/fmdita/templates/default/cqtemplates` node. Make a copy of the referenced templates in the `apps` folder before making any changes.

1.  Click the *default* component in the *templates* node to access its properties.

    AEM Guides' design template properties are described in the following table.

    |Property|Description|
    |--------|-----------|
    |`landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate`|Specify the `cq:Template` node for these corresponding pages \(landing, search, and topic\). By default the `cq:Template` node for these pages can be found in `/libs/fmdita/templates/default/cqtemplates` node. This node defines the structure and properties of the landing, search, and topic pages. <br>The `shadowPageTemplate` is used to optimize the chunked content. You need to set the value of this property to: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Note** You must specify a value for the `topicPageTemplate`. The `landingPageTemplate` and `searchPageTemplate` are optional properties. If you do not want the search and landing pages to generate, do not specify these properties.|
    |`title`|A descriptive name of your design template.|
    |`topicContentNode`|The location of the node that will contain the DITA content in a topic page. Path is relative to the topic page.|
    |`topicHeadNode`|The location of the node that will contain the head values \(or metadata\) derived from the DITA content. Path is relative to topic page.|
    |`tocNode`|The location of the node that will contain the TOC. Path is relative to the landing page or destination path.|
    |`basePathProp`|The property name for storing the path of the root of the published site.|
    |`indexPathProp`|The property name for storing the path of the landing/index page of the published site.|
    |`pdfPathProp`|The property name for storing the topic PDF path, if topic PDF generation is enabled.|
    |`pdfTypeProp`|The property name for storing the type of the PDF generation. Currently this property always contains "Topic".|
    |`searchPathProp`|The property name for storing the path of the search page, if the template includes a search page.|
    |`siteTitleProp`|The property name for storing the title of the site being published. This title is usually the same as the title of the map being published.|
    |`sourcePathProp`|The property name for storing the path of the source DITA topic for the current page.|
    |`tocPathProp`|The property name for storing the path of the TOC root for the published site.|


>[!NOTE]
>
> After creating a custom design template node, you must update the Design option in the AEM Site output presets to use the custom design template node.

For more information, see [Creating your First Adobe Experience Manager 6.3 website](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) and [The Basics](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) of developing your own website on AEM.

### Use document title for generating AEM site output 

When generating AEM Site output, the way URLs are generated play an important role in the discoverability of your content. In case you are using UUID-based file names, generating URLs based on UUID of your files would not be search friendly. As an Administrator or Publisher, you have the control on how you want to generate the URLs for your AEM Site output. AEM Guides gives you a configuration through which you can choose to generate the URLs of AEM Site output using the file's title rather than the UUID-based file names. By default, for UUID-based file systems, this option is turned ON. This implied that when you generate AEM Site output for UUID-based file systems, the file's titles are used to generate the URLs and not the UUIDs of the files.

When generating AEM Site output, the way URLs are generated play an important role in the discoverability of your content. In case of non-UUID-based file systems, the AEM Site output is generated using the file names and not the file's titles. As an Administrator or Publisher, you have the control on how you want to generate the URLs for your AEM Site output. AEM Guides gives you a configuration through which you can choose to generate the URLs of AEM Site output using the file's title rather than the file names. By default, this option is turned OFF. This implied that when you generate AEM Site output, the file names are used to generate the URLs and not the file's title. You can choose to generate the URLs based on file's titles by enabling this option.

>[!NOTE]
>
> You can further configure rules to allow only a set of character in the URLs of an AEM Site output. For more details, see [Configure filename sanitization rules for creating topics and publishing AEM Site output](#id2164D0KD0XA).

To configure the URLs generation in AEM Site output, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Use Title for AEM Site Page Names** option.

    >[!NOTE]
    >
    > In case you want to generate output using the file names, then deselect this option.

1.  Click **Save**.


### Configure filename sanitization rules for creating topics and publishing AEM Site output {#id2164D0KD0XA}

As an administrator, you can define a list of valid special characters allowed in filenames, which eventually form the URL of an AEM Site output. In earlier releases, users were allowed to define filenames containing special characters such as `@`, `$`, `>`, and more. These special characters resulted in encoded URL on generation of AEM Site pages.

Starting with 3.8 release, configurations have been added to define a list of special characters that are allowed in the filenames. By default, the valid filename configuration contains "`a-z A-Z 0-9 - _`". This implies that while creating a file, you can have any special character in the file's title, but internally it will get replaced with a hyphen \(`-`\) in the filename. For example, you can have the file's title as Introduction 1 or Introduction@1, the corresponding filename generated for both these cases would be Introduction-1.

When you define a list of valid characters, remember that these characters "`*/:[\]|#%{}?&<>"/+`" and `a space` will always be replaced with a hyphen \(`-`\).

>[!NOTE]
>
> If you do not configure the valid special characters list, the file creation process might give you some unexpected results.

To configure the valid special characters in filenames and AEM Site ouput, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.common.SanitizeNodeNameImpl* bundle.

1.  In the **Disallowed Character Set for Publishing to AEM Sites** property, ensure that the property is set to ```'<>`@$```. You can add more special characters to this list, however, it must have these required special characters.

    >[!NOTE]
    >
    > You can also configure the other properties such as **Use Lower Case** in filenames, **Separator** to handle invalid characters, and **Maximum Number of Characters** allowed in the filenames.

1.  Click **Save**.

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  In the **Regex for Valid Characters** property, ensure that the property is set to `[-a-zA-Z0-9_]`. You can add more characters to this list, however, it must have these basic characters and the list must start with a hyphen \(`-`\).

    >[!NOTE]
    >
    > This property defines the list of valid character used to create a new file.

1.  Click **Save**.


### Configure flattening of AEM Site node structure 

When you generate AEM Site output, a node for every element in the topics is created internally. For a DITA map with thousands of topics, this node structure can become too deep. This type of deeply nested node structure can have performance issues for larger sites. The following snapshot displays deeply nested node structure for an AEM Site output:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

In the above snapshot, notice that there is a node is created for every `p` element and its subsequent sub-elements and a similar structure is created for every other element used in the topic.

AEM Guides allows you to configure how AEM Site output's node structure is created internally. You can flatten the node structure at specified elements, which means that you can define an element which will be considered as the main element and all sub-elements within it will be merged with the main element. For example, if you decide to flatten the `p` element, then any element appearing within the `p` element will get merged with the main `p` element. A separate note would not be created for any sub-element within the `p` element. The following snapshot displays the node structure flattened at `p` element:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

To flatten AEM Site node structure, perform the following steps:

1.  Specify the element at which you want to flatten the node structure.

    1.  Overlay of the `libs` node in the `apps` node and open the elementmapping.xml file.

    1.  Add the `<flatten>true</flatten>` property in the definition of the element at which you want to flatten the node structure. For example, if you want to flatten the node structure at the `p` element, then add the flatten attribute in the definition of `p` element as shown below:

        ```XML
        <ditaelement>
            <name>p</name>
            <class>- topic/p</class>
            <componentpath>fmdita/components/dita/wrapper</componentpath>
            <type>COMPOSITE</type>
            <target>para</target>
            <flatten>true</flatten>
            <wrapelement>div</wrapelement>
        </ditaelement>
        ```

        >[!NOTE]
        >
        > By default, the flatten node property has been configured at the `p` element.

1.  Enable the site node flattening configuration in the configMgr.

    1.  Open the Adobe Experience Manager Web Console Configuration page.

        The default URL to access the configuration page is:

        ```http
        http://<server name>:<port>/system/console/configMgr
        ```

    1.  Search for and click on the *com.adobe.dxml.flattening.FlatteningConfigurationService* bundle.

    1.  Select the **Property flattening.enabled** option.

    1.  Click **Save**.


>[!IMPORTANT]
>
> If you have made any change in the elementmapping.xml file, ensure that you open the configMgr and save any bundle for changes to come into effect.

Now, when you generate the AEM Site output, the nodes within the `p` element are flattened and stored within the `p` element itself. You can find the new flattening properties for the `p` element in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**Prevent flattening of AEM Site note structure**

Similar to specifying the node to flatten in AEM Site output, you can also specify an element that you want to exclude from this configuration. For example, if you want to flatten nodes at `body` element, but you do not want any `table` element within `body` to flatten, then you can add the exclude property within the `table` element's definition.

To exclude the `table` element from flattening, add the following property to the `table` element's definition:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Configure the versioning for deleted pages in AEM Site output 

When you generate AEM Site output with **Delete and **Create**** option selected for the Existing Output Pages setting, a version is created for the page\(s\) being deleted. You can configure the system to stop the creation of a version before deletion.

Perform the following steps to stop the creation of a version for the page\(s\) being deleted:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Select**Do Not Create Version for Deleted Pages** option.

    >[!NOTE]
    >
    > With this option selected, users will be able to directly delete any page\(s\) without creating any version for them. If the option is not selected, then a version is created before the page\(s\) are deleted.

1.  Click **Save**.

## Use metadata in publishing output through DITA-OT {#id191LF0U0TY4}

AEM Guides provides a way to pass custom metadata while publishing output using DITA-OT. As an administrator and a Publisher you would need to perform the following tasks to configure and use custom metadata in the published output:

-   As an administrator, add the required metadata in the system so that it is made available on the Properties page of the DITA map.

-   As an administrator, add the custom metadata in the metadata list so that it shows up in the DITA map console.

-   As a Publisher, configure and add the custom metadata with the DITA map and generate the required output.


To add the required metadata in the system, perform the following steps:

1.  Log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Assets** from the list of tools.

1.  Click on the **Metadata Schemas** tile.

    The Metadata Schema Forms page is displayed.

1.  Select the **default** form from the list.

    >[!NOTE]
    >
    > The properties displayed on the Properties page for a DITA map are taken from this form.

1.  Click **Edit**.

1.  Add the custom metadata that you want to use in your published outputs. For example, we will add audience metadata using the following steps:

    1.  From the **Build Form** components list, drag-and-drop **Single Line Text** component onto the form.

    1.  Select the new field to open the **Settings** of the field.

    1.  In the **Field Label**, enter the metadata name— Audience.

    1.  In the **Map to Property** setting, specify ./jcr:content/metadata/<name of the metadata\>. For our example, we will set it to ./jcr:content/metadata/audience.

    Using these steps, add all required metadata parameters.

1.  Click **Save**.


The new parameter now shows up on the Properties page for all DITA maps.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

Next, you need to make the custom metadata available in the DITA map console. Perform the following steps to make the custom metadata available on the DITA map dash board:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Access the metadataList file available at the following location:

    /libs/fmdita/config/metadataList

    >[!NOTE]
    >
    > The metadataList file contains a list of properties that are shown in the **Properties** drop-down list of a DITA map in the map dashboard. By default, there are four properties listed in this file— docstate, dc:language, dc:description, and dc:title.

1.  Add the custom metadata that you have added in the Metadata Schema Forms page. For our example, add audience parameter to the end of the default list.

1.  Click **Save All**.


Now the custom metadata will show up in the DITA map console's **Properties** drop-down list.

Lastly, as a Publisher, you need to include the custom metadata in the published output. To process the custom metadata while generating the output, perform the following steps:

1.  In the Assets UI, navigate to the DITA map that you want to publish.

1.  Select the DITA map file and open its properties page.

1.  On the Properties page, specify the value for the custom metadata. For our example, we have specified a value of External for the audience parameter.

    ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1.  Click **Save & Close**.

1.  Click on the DITA map file to open the DITA map console.

1.  In the **Output Presets** tab, select the output preset that you want to use to generate the output.

1.  Click **Edit**.

1.  From the **Properties** drop-down list, select the properties that you want to pass on to the publishing process.

    ![](assets/props-in-publish-output.PNG){width="650" align="left"}


The selected properties/metadata are passed on to the publishing process and are made available in the final output.

## Customize DITA element mapping with AEM components {#id1679J600HEL}

DITA elements in AEM Guides are mapped to their corresponding AEM components. AEM Guides uses this mapping in workflows such as publishing and review to convert DITA element to a corresponding AEM component. The mapping is defined in the `elementmapping.xml` file, which can be accessed from the CRXDE Lite mode. Access the following URL in the CRXDE Lite mode:

`/libs/fmdita/config/elementmapping.xml`

>[!NOTE]
>
> Do not make any customizations in the default configuration files available in the ``libs`` node. You must create an overlay of the ``libs`` node in the ``apps`` node and update the required files in the ``apps`` node only.

You may use the predefined DITA element mappings, or you can map DITA elements to your custom AEM components. To use your custom AEM components, you need to understand the structure of the `elementmapping.xml` file.

### elementmapping.xml structure 

A high-level overview of the `elementmapping.xml` structure is explained below:

1.  Every DITA element is first searched for a corresponding component mapping based on the element name. For example:

    ```XML
    <ditaelement>     
       <name>**substeps**</name>  
       <class>- topic/ol task/substeps</class>  
       <componentpath>dita/components/ditaolist</componentpath>  
       <type>COMPOSITE</type>  
       <target>para</target>
    </ditaelement>
    ```

    In the above example, all `substeps` DITA elements are rendered using the `dita/components/ditaolist` component.

1.  If a DITA element does not find a match based on the name, then a match on the basis of the `class` is done. For example:

    ```XML
    <ditaelement>  
       <name>topic</name>  
       <class>**- topic/topic**</class>  
       <componentpath>fmdita/components/dita/topic</componentpath>  
       <type>COMPOSITE</type>  
       <target>para</target>  
       <attributemap> 
          <attribute from="id" to="id" />  
       </attributemap>
    </ditaelement>
    ```

    In the above example, if there is no mapping defined for the `task` element, then the `task` element is mapped to the above component because `task` is inherited from the `topic` component.

1.  When an element has a corresponding component mapping, then further processing of its child elements is determined by `type`. For example:

    ```XML
    <ditaelement>  
       <name>title</name>  
       <class>- topic/title</class>  
       <componentpath>foundation/components/title</componentpath>  
       <type>**STANDALONE**</type>  
       <target>para</target>  
       <textprop>jcr:title</textprop>
    </ditaelement>
    ```

    `type` takes the following values:

    -   COMPOSITE: element to component *mapping continues for child elements* as well.

    -   STANDALONE: child elements of the current element are *not mapped further*.

    In the above example, if the `<title>` element has any child elements, they will not be mapped to any other component. The component for `<title>` element is responsible for rendering all child elements inside the `<title>` element.

1.  If there are multiple components mapped to a single DITA element, then the best match for the element is selected. To select the best match component, domain and structural specialization of DITA elements is considered.

    If there are DITA elements with domain specialization and a component is mapped for domain specialization, then that component is given high priority.

    Similarly, if there are DITA elements with structural specialization and a component is mapped for structural specialization, then that component is given high priority.

1.  You can use `<attributemap>` in element mapping to map attribute values to the corresponding node properties.

1.  `textprop` can be used for serializing the text content of a DITA element to a node property. In addition, it can be used multiple times in an element tag to serialize the text content at multiple locations in published hierarchy. You can also customize the location and name of the target property. For example:

    ```XML
    <ditaelement> 
        <name>title</name> 
        <class>- topic/title</class> 
        <componentpath>foundation/components/title</componentpath> 
        <type>STANDALONE</type> 
        <target>para</target> 
        <textprop>**jcr:title**</textprop>
    </ditaelement>
    ```

    The above element mapping specifies that the text content of `<title>` element will be saved as value of a property named `jcr:title` on the output node.

1.  `xmlprop` can be used for serializing the entire XML for a given element to a node property. The component can then read this node property and do custom rendering. For example:

    ```XML
    <ditaelement> 
        <name>svg-container</name> 
        <class>+ topic/foreign svg-d/svg-container</class> 
        <componentpath>fmdita/components/dita/svg</componentpath> 
        <type>STANDALONE</type> 
        <target>para</target> 
        <xmlprop>**data**</xmlprop>
    </ditaelement>
    ```

    The above element mapping specifies that the entire XML markup for element `<svg-container>` will be saved as value of a property named `data` on the output node.

1.  There is a special attribute mapping to handle path resolution in output generation process. For example:

    ```XML
    <attributemap> 
        <attribute from="href" to="fileReference" ispath="true" rel="source" /> 
        <attribute from="height" to="height" /> 
        <attribute from="width" to="width" />
    </attributemap>
    ```

    For the above `attributemap`, the `href` attribute in your DITA element will be mapped to a node property named `fileReference`. Now since `ispath` is set to `true`, the output generation process resolves this path and then sets it in `fileReference` node property.

    How this resolution happens is determined on the basis of value of the `rel` attribute in attribute mapping.

    -   If `rel=source`, then value of `href` is resolved with respect to the DITA source file that is currently being processed. The value of `href` is resolved and placed in the value of `fileReference` property.

    -   If `rel=target`, then value of `href` is resolved with respect to the root publish location. The value of `href` is resolved and placed in the value of `fileReference` property.

    If you do not want any pre-processing or resolution to happen on path attributes, then you need not specify the `ispath` attribute. The value is copied as is and the component can do the required resolution.


### DITA element schema 

Following is an example of the DITA element schema in `elementmapping.xml` file:

```XML
<ditaelement>         
    <name>element_name</name>     
    <class>element_class</class>     
    <componentpath>fmdita/components/dita/component_name</componentpath>     
    <type>COMPOSITE|STANDALONE</type>      
    <attributeprop>propname_a</attributeprop>       
    <textprop>propname_t</textprop>     
    <xmlprop>propname_x</xmlprop>      
    <xpath>xpath expression string</xpath>      
    <target>head|para</target>      
    <wrapelement>div</wrapelement>      
    <wrapclass>class_name</wrapclass>      
    <attributemap>           
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

The following table describes the elements in the DITA element schema:

|Element|Description|
|-------|-----------|
|`<ditaelement>`|The top-level node for each mapping element.|
|`<class>`|The class attribute of the target DITA element for which you are writing the component. <br>For example, the class attribute for the DITA topic is: <br>`topic/topic`|
|`<componentpath>`|The CRXDE path of the mapped AEM component.|
|`<type>`|Possible values: <br>- **COMPOSITE**: Process child elements as well <br>- **STANDALONE**: Skips processing of child elements|
|`<attributeprop>`|Used for mapping serialized DITA attributes and values to AEM nodes as property. For example, if you have `<note type="Caution">` element and the component that is mapped for this element has `<attributeprop>attr_t</ attributeprop>`, then the node's attribute and value is serialized to `attr_t` property of the corresponding AEM node \( `attr_t->type="caution"`\).|
|`<textprop>propname_t</textprop>`|Save the `getTextContent()` output to property defined by `propname_t.` **Note:**  This is an optimized property.|
|`<xmlprop>propname_x </xmlprop>`|Save serialized XML of this node to property defined by `propname_x.` **Note:** This is an optimized property.|
|`<xpath>`|If XPath element is provided in the element mapping, then along with element name and class the XPath condition should also be satisfied for the component mapping to be used.|
|`<target>`|Place for the DITA element in the crx repository at specified location. <br>Possible values:<br>- **head**: Under the head node <br>- **text**: Under the paragraph node|
|`<wrapelement>`|The HTML element to wrap the contents within.|
|`<wrapclass>`|The element value to the property `wrapclass.`|
|`<attributemap>`|Container node containing one or more `<attribute>` nodes.|
|`<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />`|Maps the DITA attributes to AEM properties:<br>- **`from`**: DITA attribute name<br>- **`to`**: AEM component property name <br>- **`ispath`**: If the attribute is a path value \(for example: *image*\)<br>- **`rel`**: If the path is the source or target <br>**Note:** If `attrname` starts with `%`, then map `attrname minus '%'` to prop ' `propname`'.|

**Additional notes**

-   If you plan to override the default element mapping, it is recommended that you do not make the changes in the default `elementmapping.xml` file. You should create a new mapping XML file and place the file at another location, preferably inside custom apps folder that you create.

-   In the `elementmapping.xml` file, there are many mapping entries referencing the fmdita/components/dita/wrapper component. Wrapper is a generic component that renders relatively simple DITA constructs using properties on their site node to generate relevant HTML. It uses the `wrapelement` property to generate enclosing tags and delegates the child rendering to the corresponding components. This is useful in cases where you only want a container component. Instead of creating a new component that renders a specific container tag like `div` or `p`, you can use the Wrapper component with the `wrapelement` and `wrapclass` properties to achieve the same effect.

-   It is not recommended to save large amounts of text in String JCR properties. The optimized property type calculation in output generation ensures that large text content is not saved as string type. Instead, when content larger than a certain threshold needs to be saved, the type of the property is changed to binary. By default, this threshold is configured to 512 bytes, but can be changed in the Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) by changing the **Save as Binary Threshold** setting.

-   If you are planning to override some \(and not all\) of the element mappings, you do not have to replicate the entire `elementmapping.xml` file. You need to create a new XML mapping file and define only the elements that you are overriding.

-   After you have created the XML file in the custom location, update the `Override Element Mapping` setting in the `com.adobe.fmdita.config.ConfigManager` bundle.


## Customize DITA map console {#id188HC08M0CZ}

AEM Guides gives you the flexibility of extending the capabilities of the DITA map console. For example, if you have a set of reports that are different from what is available in AEM Guides, you can add such reports to the map console. To customize the map console, you need to create an AEM Client Library \(or ClientLib\) that will contain the code to perform the functionality that you need.

>[!NOTE]
>
> Direct modification to page components is not recommended, as it will get overwritten by new releases of the product.

AEM Guides provides the `apps.fmdita.dashboard-extn` category for customizing map console. Whenever the map console is loaded, the functionality created under the `apps.fmdita.dashboard-extn` category gets executed and loaded.

>[!NOTE]
>
> For more information about creating AEM Client Library, see [Using Client-Side Libraries](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Handle image rendition during output generation {#id177BF0G0VY4}

AEM comes with a set of default workflows and media handles to process assets. In AEM, there are pre-defined workflows to handle asset processing for the most common MIME types. Typically, for every image that you upload, AEM creates multiple renditions of the same in binary format. These renditions may be of different size, with a different resolution, with an added watermark, or some other changed characteristic. For more information about how AEM handles assets, see [Processing Assets Using Media Handlers and Workflows](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) in AEM documentation.

AEM Guides allows you to configure which image rendition to use at the time of generating output for your documents. For example, you can choose from one of the default image renditions or create one and use the same to publish your documents. Image rendition mapping for publishing your documents is stored in the `/libs/fmdita/config/ **renditionmap.xml**` file. A snippet of `renditionmap.xml` file is as follows:

>[!NOTE]
>
> It is recommended that you create a copy of the `renditionmap.xml` file in the `apps` folder for all customizations.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

The `mimetype` element specifies the MIME type of the file format. The `rendition output` element specifies the type of output format and the name of rendition \(for example, `cq5dam.web.1280.1280.jpeg`\) that should be used for publishing the specified output. You can specify the image renditions to use for all supported output formats - AEMSITE, PDF, HTML5, EPUB, and CUSTOM.

If the specified rendition is not present, then AEM Guides publishing process first looks for the web rendition of the given image. If even the web rendition is not found, then the original rendition of the image is used.

>[!NOTE]
>
> These image renditions control only the output generation. An image's web rendition is used when you open a document for preview or review.

## Configure auto-purging period for output history {#id19AAI070V8Q}

When you generate an output, the output gets created along with the output logs. For large DITA maps, these logs can take a large amount of space in your repository. By default, the logs are stored at the following location in the repository:

/var/dxml/metadata/outputHistory/

Over a period of time, the collective size of all log files could run into GBs. AEM Guides allows you to configure a time period to keep these log files in the repository. After the specified time period, the logs along with output generation history are deleted from the repository.

>[!NOTE]
>
> The output generation history is the log entry in the Generated Outputs list in the Outputs tab.

Configuring the history purging feature impacts the output generation for all DITA maps in the repository. In the Outputs tab of a DITA map, the history is purged after the specified number of days and at the time specified in the setting.

>[!NOTE]
>
> Removing the log files and output generation history does not have any impact on the generated output.

Perform the following steps to set a day and time to purge output history and logs:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  In the **Output History Purging Period** property, specify the number of days after which the output history along with output logs are purged. By default, it is set to 5 days. If you want to disable this feature, then set this property to 0.

1.  In the **Output History Purging Time** property, specify the time when the purging process is initiated. By default, it is set to 0:00 \(or 12:00 midnight\). Everyday at this time, the purging process is executed on outputs generated before the number of days specified in the **Output History Purging Period** property.

    >[!NOTE]
    >
    > By default, the purging feature is executed every midnight on outputs older than 5 days.

1.  Click **Save**.


## Change the recently generated outputs list limit {#id1679JH0H0O2}

You can change the maximum number of generated outputs that are displayed in the Outputs tab for a DITA map. By default, a list of last 25 generated outputs is shown. To change the number of outputs to display in the list, update the **Outputs List Limit** setting in the `com.adobe.fmdita.config.ConfigManager` bundle.

>[!TIP]
>
> See the *Output history* section in the Best practices guide[appendix.md\#](appendix.md#) for best practices around working with output history.

## Output generation performance optimization {#id176LB050VUI}

AEM Guides allows you to configure the output generation processes pool size that controls the number of output generation processes that run concurrently. By default, the process pool size is set to number of processing cores available in your system plus one. You might want to change this value to 1 in case you want sequential publishing. In this case, the first publishing task gets executed and the next publishing task is stored in the publishing queue.

To change the output generation processing pool size, update the **Generation Pool Size** setting in the `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` bundle.
