---
title: Configure the URL of the AEM Site output to use the document title
description: Learn how to configure the URL of the AEM Site output to use the document title

---
# Configure the URL of the AEM Site output to use the document title

You can use the document titles in the URL of the AEM Site output. If the filename doesn’t exist or contains all special characters, you can configure the system to replace the special characters with a separator in the URL of the AEM Site output. You can also configure it to replace them with the first child topic’s name.


To configure the page names, perform the following steps:

1.  Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file.
1.  In the configuration file, provide the following (property) details to configure the page names for the topics.

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.common.SanitizeNodeName`|`nodename.systemDefinedPageName`|Boolean (`true/false`). **Default value**: `false`|

For example, if the *@navtitle* in `<topichead>` has all special characters and you set the `aemsite.pagetitle` property to true, then by default, it uses a separator. If you set the `nodename.systemDefinedPageName` property to true, it shows the first child topic’s name.