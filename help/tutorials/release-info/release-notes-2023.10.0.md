---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, October 2023 release
description: Learn about the bug fixes and how to upgrade to the October 2023 release of Adobe Experience Manager Guides as a Cloud Service
---
# October 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version October 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in the October 2023 release of AEM Guides as a Cloud Service](whats-new-2023.10.0.md).

## Upgrade to October 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.10.0.373.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the October 2023 release of AEM Guides as a Cloud Service.

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

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service October 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.10.0|  3.2-uuid 5|  3.2-uuid 5 | 2.3 | 2.3 | 
|  |  |  |  |


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|AEM Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- Afternoon hours are not set in the **Date** for the creation of baselines. (12712)
- Not able to paste the JSON code in the `<codeblock>` element of the Web Editor. (12326)
- Unsaved version changes and the indicators for them are not displayed for large files. (11784)
- While editing in the Korean language, the first character changes to the default. (10049) 


### Publishing

- Native PDF | The order of the topics isn't fixed when the PDF output is generated. (13157)
- Native PDF| No default style tag is available for `<p>`element. (12559)
- Native PDF | Inline styles applied to the content region are not applied to the topics in front matter and back matter. (13510)
- The `DeliveryTarget` attribute isn't propagated on generating the AEM Site output.  (13132)
- The **Publish** workflow gets stuck while generating AEM Site output for content with certain errors. (12000)

### Management

- Version History doesn’t show even if the `dc:format` property isn't present for an asset. (10463)


### Review

- The Review on a topic shows incorrect comments. (13453)



### Translation

- The baseline exported from the **Translation** dashboard fails and doesn’t open in the target language. (13466)

- New translation projects are created instead of adding new jobs to the selected existing translation projects.  (10214)






