---
title: Verify AEM Guides installation
description: Learn how to Verify AEM Guides installation
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
---
# Verify AEM Guides installation {#id213BD030FBE}

Once you have installed AEM Guides, you need to verify whether the installation was successful or not. Perform the following steps to verify the installation:

1.  Access the Developer Console of your Cloud Service.

    For details of accessing Developer Console, see [Developer Console access](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) in AEM documentation.

1.  Access the list of OSGi Bundles in AEM.

    For details of accessing Bundles, see [Bundles](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) in AEM documentation.

1.  Search for fmdita in the list of bundles and check its status.

    The status should show *Active* for successfully deployed bundles. If any of the bundle does not have an Active status, then check the AEM logs to troubleshoot the installation issue.


**Parent topic:**[Download and install](download-install.md)
