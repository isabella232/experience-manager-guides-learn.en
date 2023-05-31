---
title: Configure valid file names for AEM Site output
description: Learn how to Configure valid file names for AEM Site output
exl-id: 33b1c54a-ca25-43e1-8261-368f5fdbc575
---
# Configure valid file names for AEM Site output {#id214GK0X0KXA}

Similar to the list of valid file name characters allowed for DITA topics, you can also configure a list of valid file name characters for AEM Site output. Some of the known characters that are not allowed in a URL are: ```'<>`@$```. These characters are configured to automatically convert into an underscore "_" when they are found while generating AEM Site output file names. The configuration that allows you to set valid characters in AEM Site output is present in the `com.adobe.fmdita.common.SanitizeNodeNameImpl` bundle. **Set the Disallowed Character Set for Publishing to AEM Sites** setting to include characters that you want to replace with an underscore in the AEM Site output file names.

**Parent topic:**[Configure filenames](conf-file-names.md)
