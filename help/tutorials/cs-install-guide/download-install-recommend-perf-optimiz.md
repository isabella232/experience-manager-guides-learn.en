---
title: Recommendations for performance optimization
description: Learn Recommendations for performance optimization
---

# Recommendations for performance optimization {#id213BD0JG0XA}

For performance optimization, consider the following points:

-   To optimize content and indexing experience, see [Optimize Content Search and Indexing](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) in AEM documentation.

-   Patch Xerces Jar while using custom DITA-OT for publishing. This is a mandatory configuration, depending on your use case. This change is required only if you use custom DITA-OT for publishing output.

    *Required configuration*: Replace the Xerces Jar file in your custom DITA-OT package with the one shipped OOTB. The default OOTB xercesImpl-2.11.0.jar file is available within the /libs/fmdita/dita\_resources/DITA-OT.zip file. Ensure that you rename the xercesImpl-2.11.0.jar file to match the old Xerces Jar file being replaced. This can be done at run time.

    This change reduces the publishing time and memory utilization while publishing DITA maps with a large number of topics.


**Parent topic:**[Download and install](download-install.md)

