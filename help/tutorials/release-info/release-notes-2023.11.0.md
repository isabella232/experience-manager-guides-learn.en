---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, November 2023 release
description: Learn about the bug fixes and how to upgrade to the November 2023 release of Adobe Experience Manager Guides as a Cloud Service

---
# November 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version November 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in the November 2023 release of AEM Guides as a Cloud Service](whats-new-2023.11.0.md).

## Upgrade to November 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.10.0.373.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the November 2023 release of AEM Guides as a Cloud Service.

## Steps to enable the trigger of a script via a servlet

(Only if you are on a version prior to the June 2023 release of AEM Guides as a Cloud Service)

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

(Only if you are on a version prior to the June 2023 release of AEM Guides as a Cloud Service)

Perform the following steps for post-processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 DITA files in the system, update the `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in the *Configuration overrides* section in Install and configure Adobe Experience Manager Guides as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the queryLimitReads option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|

1.  Run a POST request to the server (with correct authentication) - `http://<server:port>//bin/guides/reports/upgrade`.

1.  The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1.  Once the job is completed, the previous GET request responds with success. If the job fails for some reason, then failure can be seen from server logs.

1. Revert to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a version prior to the June 2023 release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1.   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered. 

1.   The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1.   Once the job is completed, the previous GET request responds with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Steps to handle the fmdita rewriter conflict

Experience Manager Guides has a custom sling rewriter module for handling cross-map links (modify the links generated in case of cross-maps). 

If you have your own sling rewriter, then use an order value that is greater than 50. For more details, view [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

To upgrade, as the order is decreasing from 1000 to 50, you need to ensure to merge the already existing rewriter, if any, correctly with fmdita-rewriter.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service November 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.11.0|  3.2-uuid 5|  3.2-uuid 5 | 2.3 | 2.3 | 
|  |  |  |  |


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|AEM Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

## Fixed issues

The bugs fixed in various areas are listed below:

### General 

- A self reference link appears under the list of Broken Links in Reports. (13539)

### Authoring

- Space after conref `<ph>` element disappears on saving the topic. (13642)
- Application error occurs on saving DITA files. (13571)
- If the title of a topic contains a slash `/`, the tab in the editor only shows the letters coming after it. (13455)
- The image preview doesn’t disappear after displaying the preview in the Editor. (13454)
- Some of the existing version or their labels are not displayed in the Version History after the upgrade to 4.x. (13247)
- Insert keyword pop-up does not appear when using root map-defined keys in other topics. (12950)
- Close icons is not visbile when very tall graphics are previewed in the Version History panel. (12867)
- Unable to modify the timezone of **Version Created On** column for the Baselines. (12711)
- The **Version History** panel in the Assets UI shows an incorrect timestamp for the **Current** field. (12624)
- Creating a DITA file from a template with a filename starting with numeric characters results in a namespace error. (12188)
- In the Web Editor, the **Key References** window opens when inserting the `varname` tag. (10940) 
- Zip files are not recognized in the Web Editor, and you cannot drag and drop them. (12709)

### Publishing

- Publish as content fragment functionality not working for files listed in search results. (14090)
- In Native PDF publishing, the background color selection on template layout requires a page reload when reverting to `None`. (13621)
- Issue in committing to datastore for a large DITA map with scope peer links in AEM Site publishing. (13530)
- Native PDF generates duplicate Table of Contents (TOC) entries in Experience Manager Guides 4.2.1 release. (12843)
- In Native PDF publishing, accessibility is compromised as images in header and footer doesn't display alt text. (12829)
- Duplicating page layout in Native PDF doesn't work with no extension added automatically. (12534)
- Custom metadata isn't available in the final output. (12116)
- fmdita rewriter conflicts with the user's rewriter config and leads to the display of long URLs instead of the links. (12076)
- With AEM Sites output preset, separate PDFs are not generated for each topic. (11555)
- Native PDF publishing lacks the support for CMYK color space conversion. (10754)
- The location of PDF Templates configuration within the Authoring Template section for output preset is not appropriate. (9981)

### Management

- Content reference is broken copy-pasting DITA files with self-reference links without GUID. (13540)
- In the Web Editor, the baseline shows the title for the previous version instead of the selected version of the DITA file. (13444)
- The **Reports** tab in the Web Editor UI fails to show the topic list for old DITA maps created prior to the 4.2 upgrade in the Cloud Servicest. (11852)
- With Experience Manager Guides installed, images with spaces in their names are not uploading to the DAM. (11718)
- Condition presets for DITA map aren't getting created. (10936)

### Review

- Side by side review panels of the previous and the current versions in the Web Editor are not correct in 4.3 release. (14156)
- Email template customization for **Review** workflow doesn't work with overlaying the nodes. (13954)
- The **Close** button on the Review page in the Experience Manager Guides takes the users to the AEM Homepage. (13535)
- Brokem characters appear while creating the snippets in Korean language. (13489)
- Korean attachments in the Experience Manager Guides Review screen are'nt clickable. (13436)
- Map title gets cut off in the review and collaboration screen, with no option to view the full title. (13012)

### Translation

- Auto approve isn't working sometimes, and exceptions occur if an incorrect value is set on **Translation Status**. (13607)
- **In Progress Projects** link returns to the wrong page. (13248)
- The baseline exported from the Translation dashboard fails and doesn't open in the target language. (12993)

