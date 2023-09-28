---
title: Native PDF | Configure JVM flags for Native PDF Publishing
description: Configure JVM flags for Native PDF Publishing
exl-id: c2342e0c-ce19-4ceb-a3e1-a6c18e3ed4e2
---
# Configure JVM flags for Native PDF Publishing

Native PDF publishing starts a separate JVM process to generate a PDF. You might have to tweak the configurations of this JVM to support different scenarios. For example, to run larger workloads you should increase the maximum heap size available to the spawned JVM process.

Perform the following steps to configure AEM Guides Native PDF Publishing JVM flags:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Java Command line options for native pdf** (*native.pdf.java.opts*) to pass any standard JVM flags.



1.  Click **Save**.
