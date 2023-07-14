---
title: Native PDF | Configure JVM flags for Native PDF Publishing
description: Configure JVM flags for Native PDF Publishing
---

# Configure JVM flags for Native PDF Publishing

Native PDF publishing uses a separate JVM process to convert the files generated in the process of publishing a final PDF file. Sometimes, you need to tweak the configurations of the separate JVM running Native PDF publishing to support different scenarios. For example, to run larger workloads you should increase the maximum heap size available to the spawned JVM process.

Perform the following steps to configure AEM Guides Native PDF Publishing JVM flags:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* bundle.

1.  Update the property **Java Command line options for native pdf** (*native.pdf.java.opts*) to pass any standard JVM flags.



1.  Click **Save**.