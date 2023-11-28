---
title: Configure page names for the topics 
description: Learn how to page names for the topics 
---
# Configure page names for the topics 

You can configure the page names for the topics. If the filename doesn’t exist or contains all special characters, then by default, the system uses a separator in the URL. You can configure the page name, to use the name of the first child topic.


To configure the page names, perform the following steps:

1.  Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file.
1.  In the configuration file, provide the following (property) details to configure the page names for the topics.

|PID|Property Key|Property Value|
|---|------------|--------------|
|`import com.adobe.fmdita.common.SanitizeNodeName`|`nodename.systemDefinedPageName`|Boolean (`true/false`). **Default value**: `false`|

For example, if the *@navtitle* in `<topichead>` has all special characters and you set the `Use title for AEM Site page names` property to true, then by default, it uses a separator. If you set the `nodename.systemDefinedPageName` property to true, it shows the first child topic’s name.