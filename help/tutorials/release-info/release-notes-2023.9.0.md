---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, September 2023 release
description: Learn about the bug fixes and how to upgrade to September 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# September 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version September 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in September 2023 release of AEM Guides as a Cloud Service](whats-new-2023.9.0.md).

## Upgrade to September 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.7.0.314.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the September 2023 release of AEM Guides as a Cloud Service.

## Steps to enable the trigger of a script via a servlet

(Only if you are on a version prior to June 2023 release of AEM Guides as a Cloud Service)

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

In the previous response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It will automatically be deleted once the job is completed, till then, you can refer to this node for the current status of the job.

Wait till this job is completed before proceeding to the next steps. 

>[!NOTE]
>
> You should check if the node is still present, and the status of the job.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steps to post process the existing content to use the broken link report 

(Only if you are on a version prior to June 2023 release of AEM Guides as a Cloud Service)

Perform the following steps for post processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 dita files in the system, update the `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in *Configuration overrides* section in Install and configure Adobe Experience Manager Guides
as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the queryLimitReads option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|

1.  Run a POST request to the server (with correct authentication) - `http://<server:port>//bin/guides/reports/upgrade`.

1.  The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1.  Once the job is complete, the previous GET request will respond with success. If job fails for some reason then failure can be seen from server logs.

1. Revert back to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a version prior to June 2023 release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1.   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered. 

1.   The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1.   Once the job is complete, the previous GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service September 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.09.0| 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 | 
|  |  |  |  |


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|XML_Documentation_Components_Content_Package_for_Cloud_Service|1.2.2| 1.0.15|

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- The topic file isn’t unlocked in the Web Editor, although the Unlock the File option and the Don’t Save option are selected. (12558)
- Unable to checkout a file in the Web Editor, despite choosing the NO option to discard the changes before check-in. (12557)
- The tooltips for the Lock & Unlock file icons in the main toolbar within the Web Editor are not consistent with the icons displayed in the Repository View.(12555)
- Cancel check out and Unlock option is displayed for a file in the Web Editor that isn’t yet checked out in Map View. (12556)
- Unable to select the PDF assets in the existing "topicref" links. (12477).
- In the Repository View, the topics or images cannot be dragged after using the Search/Filter functionality. (12396)
- Search results are disabled in the Find and Replace panel after opening one searched file. (12142)
- The “8” number key on the side keyboard isn’t working in the AEM Guides editor. (12106)

- The prefix is duplicated in the preview mode of the Web Editor. (13133)
- `Choicetable` rows are not displayed or cannot be selected. (12616)
- The Web Editor throws validation errors in specific scenarios when creating a topic using a custom schema. (12576)
- The ditaval topic template references don’t create a copy in the content folder when creating a map from the map template. (12150)
- The search box in DITA maps does not have a close button. (11867)
- On saving long files in the Web Editor, `DirtyChecker` throws an exception with a long stack trace and fills the log files. (11860)
- The Reports tab in Web Editor doesn’t display the topic list of old DITA maps created before the 4.2 upgrade. (11852)
- Creating DITA topics requires Delete permission on the corresponding folder node, although the map can be created with Write permission. (11706)


### Management

- The "title" field in DITA map metadata properties is overwritten by `<title>` element for the map. (10702)


### Publishing

- Publishing fails on renaming a Native PDF preset. (12564)
- Duplicating a Native PDF template duplicates to the default template location instead of the provided custom template location. (12563)

- Native PDF | Including multiple xrefs extends the text beyond the column width. (13004)
- Native PDF | In AEM Guides version 4.2.1.270, when the topic and title have the same ID, it leads to a malformed generation of the PDF output. (12644)
- Native PDF | On adding an outputclass to a parent `<topicref>` element in a DITA map and applying custom style to the outputclass, the styling is applied to elements within the topic body, including section titles.(12166)
- Incremental publishing doesn’t work if a DITA map has multiple ditavalrefs. (12117)
- AEM Site | On creating a map with keydef pointing to a topic as a variable and adding processing-role=resource-only creates some unexpected pages. (12099)
- If any assets from AEM’s DAM are used in any output other than the AEM site, then the metadata "jcr:createdBy" does not reflect the publisher’s name or the name of the user who last modified the DITA map or topic. (12090)
- AEM Sites | DITA map with topichead in the navtitle (with non-supported characters) leads to bad page URLs. (11978)
- Native PDF | Issues occur in support of topichead / topicmeta / navtitle in Frontmatter and Backmatter. (11969)
- Native PDF | Generating PDFs for large documents is time-consuming. (11955)
- Native PDF | Renaming a preset throws a NullPointerException while generating a PDF output. (11889)
- The `<conref>` content isn’t shown in the PDF output. (11131)
- Web Editor shows an incorrect title when a slash is present. (10949)
- An extra space gets added inside the `<div>` elements on toggling between the Author and Source view in the page layout editor. (10750)
- The content replicated on the AEM Cloud manager isn’t visible on the Publish instance. (9564)

### Translation
The  process to export a baseline fails. (12993)




