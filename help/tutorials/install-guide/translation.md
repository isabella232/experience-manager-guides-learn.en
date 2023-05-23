---
title: Translate content in AEM Guides
description: Learn how to Translate content
---

# Translate content {#id181GB0400UI}

Automate the translation of page content, assets, and user-generated content to create and maintain multilingual websites. To automate translation workflows, you integrate translation service providers with AEM and create projects for translating content into multiple languages. AEM supports human and machine translation workflows.

-   Human translation: Content is sent to your translation provider and translated by professional translators. When complete, the translated content is returned and imported into AEM. When your translation provider is integrated with AEM, content is automatically exchanged between AEM and the translation provider

-   Machine translation: The machine translation service immediately translates your content


Translating content involves the following steps:

1.  Connect AEM with your [translation service provider](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) and create [translation integration framework configurations](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1.  Associate the pages of your language master with the [translation service and framework configurations](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1.  Identify the type of [content to translate](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1.  [Prepare the content for translation](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) by authoring the language master and creating the root pages of language copies.

1.  Create [translation projects](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) to gather the content to translate and to prepare the translation process.

1.  Use the translation projects to [manage the content translation](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) process.


When your translation service provider does not provide a connector to integration with AEM, then AEM supports the manual export and import of translated content in XML format.

>[!TIP]
>
> See the *Translation*s ection in the Best practices guide for best practices around translating content.

## Configure the Translation tab on the DITA map dashboard 

The Hide Translation Tab option is not enabled by default and you need to enable this from the configMgr. To hide the Translation tab on the DITA map dashboard, perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Hide Translation Tab** option, to hide the translation tab on the map dashboard.

    >[!NOTE]
    >
    > This property is disabled by default and the translation tab is available on the map dashboard.

1.  Click **Save**.

## Configure component-based translation workflow 

If the connector for the translation vendor does not support DITA content, then the component-based translation workflow needs to be enabled. Once enabled, the translatable content is sent as asset metadata. However, the connector needs to support asset metadata translation for this workflow to work.

Based on the translation workflow used in your setup, the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Configure the **Component-Based DITA Translation Workflow** option as per your setup:

    -   If you are using human translation, then *Disable* the **Component-Based Translation Workflow** option.

    -   If you are using machine translation, then *Enable* the **Component-Based Translation Workflow** option.

    >[!NOTE]
    >
    > If you are using translation connector, then ensure that you have configured the connector as described in the *[Configuring the Translation Integration Framework](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* topic in AEM documentation.

1.  Click **Save**.


>[!IMPORTANT]
>
> After setting up the translation configurations, ensure that you set up the appropriate Cloud Configuration on the language folders.

## Configure post-processing of temporary language copies 

When you initiate the translation workflow, the system creates temporary language copies of the source content. You can choose to enable or disable the post-processing operation on these temporary files. In the post-processing operation, the incoming and outgoing references from the files are resolved, the document state is set, along with other operations. If you enable post-processing on these temporary files, the translation process could take longer time to complete. Therefore, it is recommended to keep post-processing option disabled.

By default, the post-processing of temporary files option is disabled. You can configure this option by perform the following steps:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Configure the **Post-process language copies** option as per your setup:

    -   \(*Default*\) If you do not want to run the post-processing operation on the temporary files, then *Disable* the **Post-process language copies** option.

    -   If you want to run the post-processing operation on the temporary files, then *Enable* the **Post-process language copies** option.

1.  Click **Save**.


