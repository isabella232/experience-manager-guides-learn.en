---
title: Configure valid file names for AEM Site output
description: Learn how to Configure valid file names for AEM Site output
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
---
# Configure valid file names for AEM Site output {#id214GK0X0KXA}

Similar to the list of valid file name characters allowed for DITA topics, you can also configure a list of valid file name characters for AEM Site output. Some of the known characters that are not allowed in a URL are: ``'<>`@$``. These characters are configured to automatically convert into an underscore "`_`" when they are found while generating AEM Site output file names.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to set valid characters in AEM Site output:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.common.SanitizeNodeNameImpl`|`aemsite.DisallowedFileNameChars`|Add characters that you want to replace with an underscore in the AEM Site output file names. <br> **Default value**: ``'<\>\`@$``|

**Parent topic:**[Configure filenames](conf-file-names.md)
