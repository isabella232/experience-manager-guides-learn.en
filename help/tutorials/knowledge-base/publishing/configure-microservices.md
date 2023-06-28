---
title: Configure new microservice-based publishing for AEM Guides as a Cloud Service
description: Learn how to Configure new microservice-based publishing for AEM Guides.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
---
# Configure new microservice-based publishing for AEM Guides as a Cloud Service

The new publishing microservice enables users to run large publishing workloads concurrently on AEM Guides as a Cloud Service and leverage the industry leading Adobe I/O Runtime serverless platform.

For each publishing request AEM Guides as a Cloud Service runs a separate container which scales horizontally as per the user requests. This provides users the capabilities to run multiple publishing request and get performance better than their large on-prem AEM servers.

>[!NOTE]
>
> Microservice-based publishing in AEM Guides supports PDF (both Native and DITA-OT based), HTML5, and CUSTOM types of output presets.

As the new cloud publishing service is secured by Adobe IMS JWT based authentication, customers should follow the below given steps to integrate their environments with Adobe's secure token-based authentication workflows and start using the new cloud based scalable publishing solution.


## Create IMS configurations in Adobe Developer Console

**Role required to create the confugrations**: System Administrator

Perform the following steps to create IMS configurations in Adobe Developer Console:

1. Open Developer Console: `https://developer.adobe.com/console`.

1. Switch to **Projects** tab from top.

    <img src="assets/projects-tab.png" alt="projects tab" width=500>

1. To create a new empty project, select **Empty project** from the **Create new project** dropdown.

    <img src="assets/create-new-project.png" alt="create new project" width=500> 

1. Select **API** from the **Add to Project** dropdown to add IO Management API to your project.

    <img src="assets/add-project.png" alt="add project" width=300> 

    <img src="assets/io-management-api.png" alt="io management" width=500>

1. Create a new private/public key pair while adding the API. This will automatically download the private key on your system.

    <img src="assets/generate-key-pair.png" alt="generate key pair" width=500> 

1. Save the configured API.

    <img src="assets/save-api.png" alt="save api" width=600> 
 
1. Go back to **Projects** tab and click **Project overview** on the left. 

    <img src="assets/project-overview.png" alt="project overview" width=500> 

1. Click **Download** button on  the top to download the service JSON.

    <img src="assets/download-json.png" alt="download json" width=500> 

You have now configured the JWT authentication details and have also downloaded the private key and the service details JSON. Keep these two files handy as these files are required in the next section.

### Add IMS configuration to the environment

Perform the following steps to add IMS configuration to the environment:

1. Open experience manager and then select your program  which contains the environment  you want to configure.
1. Switch to **Environments** tab.
1. Click on the environment name which you want to configure. This should navigate you to the Environment Information page.
1. Switch to **Configuration** tab.
1. Upload the private key and project JSON as shown in  the screenshot  below. Make sure you are using the same names and configuration as highlighted below.

    <img src="assets/ims-config-environment.png" alt="ims configurations" width=500>

>[!NOTE]
>
> You need to open, copy, and  paste the contents of private key and service details JSON file to the value column of the  Configuration panel as shown in the above screenshot.

Once you have added the IMS configuration to the environment, perform the following steps to link these properties with AEM Guides using OSGi: 

1. In you cloud manager Git project code, add the below given two files (For file contents, see [Appendix](#appendix)).

    * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
    * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Ensure that the newly added files are getting covered by your `filter.xml`.
1. Commit and push your Git changes.
1. Run the pipeline to apply the changes on the environment.

Once this is done, you should be able to use the new microservice-based cloud publishing.

## FAQs

1. Can a single key be used on multiple cloud environments?
    * Yes, you can generate one private key and use it for all environments, but you have to configure environment variables for all environments and use same key.
1. If we commit the configurations to enable microservice, will the publishing process work on my local with the same codebase?
    * No, if the flag `dxml.use.publish.microservice` is set to `true` then it always look for microservice configurations. You have to set `dxml.use.publish.microservice` to `false` for the publishing to work on your local.
1. How much memory is allocated to the DITA process when using microservice base publishing? Is this driven via DITA profile ant parameters?
    * With microservice-based publishing, memory allocation is not driven through DITA profile ant parameters. Total memory available on the service container is 8 GB, out of which 6 GB is allocated to the DITA-OT process


## Appendix {#appendix}

**File**: 
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Content**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**File**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Content**:
* `dxml.use.publish.microservice`: Switch to enable microservice-based publishing using DITA-OT
* `dxml.use.publish.microservice.native.pdf`: Switch to enable microservice-based Native PDF publishing

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
