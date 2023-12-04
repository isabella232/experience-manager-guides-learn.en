---
title: Upgrade AEM Guides
description: Learn how to Upgrade AEM Guides
---
# Upgrade AEM Guides {#id213BD050YPH}

1.  Access your Cloud Manager's Git repository.

1.  Update the dox/dox.installer/pom.xml file.

1.  Update the value of dox.version variable to the version details provided by Adobe.

1.  Commit the changes and run the Cloud Manager pipeline to deploy the upgraded package.


>[!NOTE]
>
> For more details about using CI/CD pipeline, see [Use the CI/CD Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Clear browser cache 

After completing the upgrade process, all users must clear the browser cache before using the upgraded version of AEM Guides.

**Parent topic:**[Download and install](download-install.md)
