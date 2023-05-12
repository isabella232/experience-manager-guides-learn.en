---
title: Non-UUID to UUID content migration
description: Learn how to Non-UUID to UUID content migration
---

# Non-UUID to UUID content migration {#id226TI0U20XA}

>[!IMPORTANT]
>
> You can migrate your non-UUID content to UUID server. To migrate to UUID server you should have non-UUID server with AEM guides version 4.0 installed on it.

Perform the following steps to migrate your non-UUID content:

>[!NOTE]
>
> Each step is crucial and missing any of the steps may lead to failed or corrupt server data. Ensure that you complete all the steps.

1.  Ensure that **Enable Post Processing Workflow Launchers** in *com.adobe.fmdita.config.ConfigManager* and **Enable Version Postprocessing** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation* are enabled.

    ```http
    http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
    ```

1.  Install the UUID version of the next major release over non-UUID version. For example, if you are using 4.0 non-UUID build then you need to install UUID version 4.1.

1.  In the Launcher tab, disable the following workflows and any other workflow that runs on /content/dam using launchers in `http://localhost:4502/libs/cq/workflow/content/console.html`:

    -   **DAM Update Asset** workflow
    -   **DAM Metadata Writeback** workflow

1.  Disable **Enable Post Processing Workflow Launchers** in *com.adobe.fmdita.config.ConfigManager* and disable **Enable Version Postprocessing** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation*.

    ```http
    http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
    ```

1.  Add a separate logger for `com.adobe.fmdita.uuid.upgrade.UuidUpgrade.`

    The browser response is also available at /content/uuid-upgrade/logs.

1.  Run the given query on a folder with smaller data with `doReviews=false` before running it on / content/dam: `http://localhost:4502/bin/dxml/uuid_upgrade?root=/content/dam/test&doReviews=false`

    >[!TIP]
    >
    >  You can check whether all files in the folder are upgraded properly and all features are working only for that folder.

   **Parameters for the query:**

    - `root`: Root folder where upgrade has to happen \(Use /content/dam for all repository.\)
    - `doReviews`: true/false \(If reviews have to be upgraded or not. Default value is false.\)
    - `doBaselines`: true/false \(If baselines have to upgraded or not. Default value is true.\)
    - `processLevel`: -1\(failed without restore\), 0\(failed with restore\), 1\(failed with errors\), 2\(successfully upgraded\) \(When retrying script after failure, only files with "fmUpgradeStatus" <= processLevel will be processed again, otherwise its ignored. Default value is 1.\)
    - `ignoreImageVersions`: true/false \(Ignores processing of image versions. Default value is false.\)
    >[!NOTE]
    >
    > We can run content migration on folder level or the complete content/dam or on the same folder \(rerun migration\).

1.  Once the server is migrated successfully enable the following workflows and post-processing to continue working on the server:

    -   **DAM Update Asset** workflow
    -   **DAM Metadata** workflow

>[!NOTE]
>
> If some files are not processed or are corrupted before migration, they would remain corrupted even after migration.

