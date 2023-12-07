---
title: Convert non-UUID  content with versions to UUID content
description: Learn how to migrate non-UUID content with versions.
exl-id: 9387e0d1-906c-4e5c-a7a0-0ed1600f5eb6
---
# Migrate non-UUID content with versions

Perform these steps to migrate your non-UUID content with versions to UUID content. 

## Compatibility matrix

|Current AEM Guides version (non-UUID)|Required Version to migrate to UUID| Supported Upgrade path| 
|---|---|---|
| 3.8.5|  4.0 non-UUID|Install 4.1 (UUID) and run the migration|
|4.0, 4.0.x, 4.1, or 4.1.x  | Same as current non-UUID| Install 4.1 (UUID) and run the migration|
|4.2 or Higher|   NA |Not supported yet|

## Required packages

1. **Version purge**: `com.adobe.guides.version-purge-1.0.11.zip` (optional)
1. **Pre-migration**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migration**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Post migration**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Pre-migration

1. (Optional) Perform version purging on the content to remove unnecessary versions and speed up the migration process. To perform version purging on version 4.1 (NOT supported on 4.0), install the package `com.adobe.guides.version-purge-1.0.11.zip`, and go to the user interface using this URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`. 

    >[!NOTE]
    >
    >This utility does not remove any versions used in baselines or reviews or has any labels.
1. Install the pre-migration package (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Run the following below query to get a report with an estimated time (ETA) of how long the migration will take and it reports if there are any files with content issues that would not migrate. 

>[!NOTE]
>
>You need administrator permission to execute the migration. 


|Endpoint URL| Request Type|Query Param| Expected Results|
|---|---|---|---|
|`/bin/guides/pre_uuid_upgrade` <br> <br>**For example**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam| GET| **root**: Root folder<br> **Value**: `/content/dam` for the entire repository.|A pre-migration report (.csv) will be created listing the number of files, total versions, and the errors. <br><br> **Sample output**:<br>RootFolder: /content/dam <br>Total Files: 2697 <br>Total Versions: 10380 <br>Number of files with errors: 28 <br>A detailed report will be available via AEM CRX at `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv`|

This step could fail if there are many DITA files in the system. To address this, increase the limit of the number of files traversed in the query by increasing the value of *In Memory Read Limit (queryLimitReads)* in Apache Jackrabbit Query Engine Settings Service from 100000  a number greater than the total number of DITA assets present in the system.

## Migration 

### Step 1: Update configuration

1. Ensure that the free space available is at least 10 times the space taken by AEM (crx-quickstart directory) during migration. Once you complete the migration , you can reclaim most of the disk space by running compaction (refer to [Revision Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Enable *Enable Post Processing Workflow Launchers* in `com.adobe.fmdita.config.ConfigManager` and *Enable Version Postprocessing* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Install the UUID version of the supported release over the non-UUID version. For example, if you're using a 4.0 non-UUID build or a 4.1 non-UUID build, you need to install UUID version 4.1.

1. Install the new package for uuid migration (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Disable the following workflows and any other workflow that runs on `/content/dam` using launchers in `http://localhost:4502/libs/cq/workflow/content/console.html`.

    * DAM Update Asset workflow
    * DAM Metadata Writeback workflow

1. Disable *Enable Post Processing Workflow Launchers* in `com.adobe.fmdita.config.ConfigManager` and disable *Enable Version Postprocessing* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`. 

1. Disable the property Enable validation (`validation.enabled`) in Day CQ Tagging Service.

1. Ensure that `uuid.regex` property folder is set properly in `com.adobe.fmdita.config.ConfigManager`. If it's blank, set it to the default value - `^GUID-(?<id>.*)`.
1. Add a separate logger for `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` The browser response is also available at `/content/uuid-upgrade/logs`.

### Step 2: Run the script and validate

Run the given query on a folder with smaller data before running it on `/content/dam`.

>[!TIP]
>
>You can check whether all files in the folder are upgraded properly and whether all features work only for that folder.

|Endpoint URL|Request Type|Query Param|Expected Results|
|---|---|---|---|
|`/bin/guides/uuid_upgrade`<br><br> **For example**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test`| GET|**root**: Root folder <br>**Value**: /content/dam for the entire repository.<br><br>**ignoreImageVersions**<br> **Value**: true/false (Ignores processing of image versions. The default value is false) |Migration report with List of files migrated successfully, failed to upgrade, upgraded with errors, and total time taken. <br><br> **Sample output**: <br> [INFO] List of files failed:0 <br>[INFO] No. of files upgraded successfully: 2241 <br>[INFO] No. of files upgraded with errors: 28 <br>[INFO] No. of files failed to upgrade: 0 <br> [INFO] Total time taken: 0:37:03.131|

>[!NOTE]
>
> Content migration can be run on a folder level or the complete `/content/dam` or on the same folder (rerun migration).

Additionally, it's important to make sure that the content migration is also done for all the media assets, such as images and graphics that you have used in the DITA content.

#### Baseline migration

Run the query on the folder that you have already migrated to migrate the baselines on it. 

|Endpoint URL| Request Type| Query Param|Expected Results|
|---|---|---|---|
|`/bin/guides/baseline_uuid_upgrade`<br><br> **For example**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test`|GET|**root**: Root folder <br> **Value**: /content/dam for the entire repository. <br><br> **ignoreImageVersions**<br> **Value**: true/false <br>(Ignores processing of image versions. The default value is false) <br><br> **doReviews** <br> **Value**: true/false <br> (If reviews must be upgraded or not. The default value is false.) Migration report with List of files migrated successfully, failed to upgrade, upgraded with errors, and total time taken. <br> <br> **Sample output**:<br>[INFO] List of files failed <br> [INFO] No. of files upgraded successfully 2241<br> [INFO] No. of files upgraded with errors 28<br>[INFO] No. of files failed to upgrade 0<br>[INFO] Total time taken: 0:37:03.131|


### Step 3: Restore the configuration

Once the server is migrated successfully, enable post-processing, tagging, and the following workflows (including all the other workflows which are disabled initially during the migration) to continue working on the server.

* DAM Update Asset workflow
* DAM Metadata workflow

>[!NOTE]
>
>If some files are not processed or be corrupted before migration, and they would be corrupted before migration and remain corrupted even after migration.

## Migration validation

1. Install the post uuid migration package (`com.adobe.guides.post-uuid-migration-1.0.2.zip`). 

1. Run the following query to validate that there were no errors during migration that caused any links to be broken. This script will identify if there were any links which were not broken before but have been broken now for any reason.

    |Endpoint URL| Request Type|Query Param|Expected Results|
    |---|---|---|---|
    |`/bin/guides/get_broken_links` <br> <br> **For example**:<br>`http://localhost:4502/bin/guides/get_broken_links`|GET|NA|Migration report with the total number of files having broken UUIDs and their respective file paths. <br> <br> **Sample output**:<br>[DEBUG] Checking if all these GUIDs are used in the content.<br>[DEBUG] Total number of files potentially having broken UUIDs: 0 <br>[DEBUG] Paths potentially having broken UUIDs:0|

1. Once the migration is completed, most of the disk space can be reclaimed by running compaction (refer to `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Delta content migration

1. To migrate the delta content from the active server (non-UUID) to the current uuid server, install the pre-migration script on the non-UUID server.

1. Run the following query on the entire data set (or subfolder) to identify and export all the files modified after the given timestamp:
The timestamp uses the ISO8601 format for dates and times ( YYYY-MM-DDTHH:mm:ss.SSSZ) and also allows partial representations, like YYYY-MM-DD.

    |Endpoint URL|Request Type|Query Param|Expected Results|
    |---|---|---|---|
    |`/bin/guides/data_export`<br><br>**For example**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam`| GET|**timestamp** <br> **Value**: YYYY-MM-DD<br><br> **root**: Root folder <br> **Value**: `/content/dam` for the entire repository. | A zip file with delta content gets created at /var/dxml/exports. <br> <br>**Sample**: dataexport_1689761491218.zip (file gets created)|

1. Download the zip file exported by the script. The last line of the response should give the path of the generated zip file (stored in /var/dxml/exports in the system).

1. Upload the zip file to the uuid server at the desired path in Assets UI.

1. Ensure the post-migration package is installed on the uuid server. 

1. Run the following given query to import the delta content from the uploaded zip file into the system. The query should include the path of the uploaded zip file to properly identify and process the data.

    |Endpoint URL|Request Type|Query Param|Expected Results|
    |---|---|---|---|
    |`/bin/guides/data_import`<br> **For example**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true`|POST|**path**<br> **Value**: `/content/dam/filename.zip`(Uploaded file location) **createVersion** <br> **Value**: true/false<br>(The default value of createVersion is false).|The file gets uploaded to the desired content path.<br><br>**Sample**: `dataexport_1689761491218.zip`<br><br> (The same file which was exported in the previous step gets uploaded to the desired path in `/content/dam`).|

1. The script will create a new file if it doesn't exist or override the existing file if it was modified. 

>[!NOTE]
>
> The version history and any other changes made on the server (like workflows and reviews ) need to be manually updated.
