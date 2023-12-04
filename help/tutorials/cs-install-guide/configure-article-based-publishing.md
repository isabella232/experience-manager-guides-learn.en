---
title: Install packages for Article-based publishing
description: Learn how to Install packages for Article-based publishing
---
# Install packages for Article-based publishing {#id21BNL02052Z}

AEM Guides provides a powerful article-based publishing feature integrated with the Web Editor. Using this feature, you can publish one or more topics simultaneously. Once you have opened a map in the Map Editor, you can navigate to the Outputs tab to create a preset, and then choose one or more topics to generate the output. You can use the article-based publishing feature to incrementally generate output of one or more topics or publish your content to a knowledge base platform in an article-by-article fashion. For more details see, *Article-based publishing from the Web Editor section* in the User guide.

To create an AEM site for publishing article-based output, perform the following steps:

1.  Download **XML Documentation Components Content Package for Cloud Service** from your [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1.  Open AEM Package Manager. The default URL to access the package manager is: `https://<hostname>/crx/packmgr/index.jsp`
1.  Upload XML Documentation Components Content Package for Cloud Service and then install it.
1.  Download the `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` file from your [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1.  From the Global Navigation, select **Sites**.
1.  Within the Sites UI, click **Create** button on the top-right corner.
1.  Select **Site from template** from the **Create** dropdown.
1.  Click the **Import** button and then select the `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` downloaded on your system. Once the site template is imported it listed at the bottom.

    >[!NOTE]
    >
    > You need to import the ZIP file only for the first time. Once imported, the site template is available in the list.

    Select **Knowledge base template for Article-based publishing** to create the AEM site and click **Next** on the top-right corner.

1.  Enter the **Site title** and the **Site name** and click **Create** on the top-right corner. An AEM site is created using the Tragopan site template. \(Tragopan site is a sample knowledge base AEM site with templates for a category, section, and article pages.\)

    >[!NOTE]
    >
    > You can create multiple AEM sites using the same template.


You can use the AEM site to publish your article using the output presets from the Web Editor.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
