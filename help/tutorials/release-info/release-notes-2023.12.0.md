---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, December 2023 release
description: Learn about the bug fixes and how to upgrade to the December 2023 release of Adobe Experience Manager Guides as a Cloud Service.

---
# December 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version December 2023 of Adobe Experience Manager Guides as a Cloud Service (later referred as *Experience Manager Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in the December 2023 release of Experience Manager Guides as a Cloud Service](whats-new-2023.11.0.md).

## Upgrade to December 2023 release

Upgrade your current Experience Manager Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.11.0.406.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the December 2023 release of Experience Manager Guides as a Cloud Service.

## Steps to enable the trigger of a script via a servlet

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

After you complete the installation, you can choose to HIT the trigger to start the translation job:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Response: 

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In the previous response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It will automatically be deleted once the job is completed, then, you can refer to this node for the status of the job.

Wait till this job is completed before proceeding to the next steps. 

>[!NOTE]
>
> You should check if the node is still present, and the status of the job.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steps to post process the existing content to use the broken link report 

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for post-processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 DITA files in the system, update the `queryLimitReads` and `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in the *Configuration overrides* section in Install and configure Adobe Experience Manager Guides as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the `queryLimitReads` and `queryLimitInMemory` option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitInMemory|Value: 200000 Default Value: 100000|

1.  Run a POST request to the server (with correct authentication) - `http://<server>//bin/guides/reports/upgrade`.

1.  The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1.  Once the job is completed, the previous GET request responds with success. If the job fails for some reason, then failure can be seen from server logs.

1. Revert to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1.   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered. 

1.   The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`\)


1.   Once the job is completed, the previous GET request responds with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Steps to handle the `'fmdita rewriter'` conflict

Experience Manager Guides has a [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module for handling the links generated in case of cross-maps (links between the topics of two different maps).

If you have another custom sling rewriter in your codebase,  use an `'order'` value greater than 50, as Experience Manager Guides sling rewriter uses `'order'` 50.  To override this, you need a value >50. For more details, view [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

During this upgrade, since the `'order'` value is changed from 1000 to 50, you need to merge the existing custom rewriter, if any, with `'fmdita-rewriter'`.


## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides as a Cloud Service December 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| Experience Manager Guides Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| Experience Manager Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.12.0|  3.2-uuid 5|  3.2-uuid 5 | 2.3 | 2.3 | 
|  |  |  |  |


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

## Fixed issues

The bugs fixed in various areas are listed below:



### Authoring

- The **Title** in the Web Editor tab gets truncated after a dot **(.)** character. (14372)
- Error messaging for duplicate map names in Assets UI needs to be updated. (14320)
- An error occurs in version creation logic during drag-and-drop of assets. (14291)
- Re-usable content skips element **IDs**.(14213)
- Lack of setting control to hide Language Variables panel under Output tab.(14194)
- In Web Editor's Layout view with specialized schema, adding a new reference **(empty/topic)** results in an application error.(14094)
- An anchor link to `<dlentry>` or `<dt>` element fails to display text.(13543)
- Favorites collection in Web Editor fails to load.(13495)
- Citations display non-clickable links when created with a unique ID with spaces.(13447)
- In Layout view for Bookmap, using **move right** to make a selected chapter a sub-element does not work.(12567)
- XML Editor's Preview window cuts off content in Google Chrome and Microsoft Edge browsers. (10755)
- The Web Editor lacks the ability to wrap an element inside possible parent elements. (8791)

### Publishing

- Fmdita components have a hardcoded path of delegator.jsp, preventing the overlay of AEM Sites components. (13993)
- PDF reactor tagged view in Native PDF publishing output isn't working as expected. (13622)
- AEM Site publishing encounters an issue committing to the datastore for large maps with scope peer links. (13531)
- Unable to activate a site using AEM Guides Bulk Publication dashboard. (13439)
- Localization of element labels isn't functioning in AEM Sites output. (12144)
- Missing **ditaval** option in folder profile level output presets created via Web Editor UI. (11903)

### Management

- AEM Cloud environments encounter **MongoWrite Exception** due to large-sized nodes.(13509)

### Translation

- **Accept/Reject** buttons erroneously appear for auto-approved human translation.(14318)
-Internationalization (i18n) issues during the transformation of non-English DITA files to AEM pages. (14286)
- Translated contents fail to sync from temporary translation projects despite translation jobs reaching the **'approved'** state, with DITA XML editor translation wizard status incorrectly showing **'In progress'**. (9938)

### Accessibility

- Unable to navigate through the author canvas user interface, as the focus becomes trapped in the Topic Editor.(13517)

