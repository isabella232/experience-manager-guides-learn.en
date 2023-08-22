---
title: Publish a topic to a content fragment
description: Learn how to publish a topic to a content fragment.
---

# Publish to a content fragment

Content fragments are discrete pieces of content in AEM. They are structured content based on a content model. Content fragments are pure content without design or layout information. They can be authored and managed independently of the channels that AEM supports. Content fragments are modular, where content is broken down into smaller components.

AEM Guides allows you to publish a topic or the elements within a topic to a content fragment. You can create a JSON-based mapping between a topic and a content fragment model. Use this mapping to publish a topic or the elements within a topic to a content fragment. You can then use content fragments in any AEM site or extract the details via APIs supported by content fragments.


To create a content fragment, perform the following steps:

1. Create a [content fragment model](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) in AEM Assets. 
1. Create a folder where you want to save the content fragments that you create based on the content fragment model. For example, "stock-content-fragments". 
1. Edit the folder’s properties (for example, "stock-content-fragments") and add the path of the folder, which contains the content fragment model in the cloud configuration. 
For example, add `/conf/we-retail` in the cloud configuration. This configuration connects all the content fragment models with the folder.       
 ![add cloud configuration details in the folder properties](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
       *Add the cloud configuration in the folder properties to connect it with the fragment models.* 
1. Select the topic that you want to publish in the **Repository View**. 
1. From the **Options** menu, select **Publish As** > **Content Fragment**.  
1. In the **Publish As Content Fragment** dialog, fill in the following details:
        ![Add the fragment model and mapping details in the Publish as content fragment dialog](images/content-fragment-publish.png){width="500" align="left"}
       *Add the path, model, and mapping details to publish a topic or its elements as a content fragment. You can overwrite an existing content fragment.*  

    * **Path**: Browse and select the path of the folder where you want to publish the content fragment. You can also select an existing content fragment and publish it.
    * **Title**: Enter the title of the content fragment.
    * **Name**: Enter the name of the content fragment.
    * **Model**: Select the content fragment model that you want to use to create your content fragment. The models are picked from the folder which you have configured in the cloud services. 
    * **Mapping**: Select a mapping from the drop-down. It picks the mappings from the *contentFragmentMapping.json* file.  

      

        Based on your setup your administrator can add the mappings in the *contentFragmentMapping.json* file. 
    
        <details>
        <summary>Cloud Services</summary>
     
         Learn more about how to [create a mapping between a topic and a content fragment](../cs-install-guide/conf-content-fragment-mapping.md) in the  Cloud Services Installation and Configuration Guide. 
        </details>

        <details>
        <summary> On-premise  Software</summary>

        Learn more about how to [create a mapping between a topic and a content fragment](../install-guide/conf-content-fragment-mapping.md) in On-premise Installation and configuration Guide.

        </details>
    * Select the **Overwrite** checkbox if your content fragment already exists and you wish to overwrite it. AEM Guides displays an error if you don’t select the checkbox and your content fragment already exists. 
1. Click **Create** to publish the content fragment.
1. You can view the content fragments for a topic under the **Fragments** section in the **File properties**.
 
    ![View the content fragments for a topic](images/topic-content-fragments.png){width="300" align="left"}
       
     *View the content fragments present for a topic and republish them.*  

You can also republish the content fragment to update the content fragment with the latest content from the DITA topic.



Once you’ve published the content fragments, you can also use them in any AEM site. 

