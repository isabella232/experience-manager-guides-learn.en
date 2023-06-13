# Translate content {#id181GB0400UI}

Automate the translation of page content, assets, and user-generated content to create and maintain multilingual websites. To automate translation workflows, you integrate translation service providers with AEM and create projects for translating content into multiple languages. AEM supports human and machine translation workflows.

-   Human translation: Content is sent to your translation provider and translated by professional translators. When complete, the translated content is returned and imported into AEM. When your translation provider is integrated with AEM, content is automatically exchanged between AEM and the translation provider

-   Machine translation: The machine translation service immediately translates your content


Translating content involves the following steps:

1.  Connect AEM with your [translation service provider](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) and create translation integration framework configurations.

1.  Associate the pages of your language master with the translation service and framework configurations.

1.  Identify the type of [content to translate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1.  [Prepare the content for translation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) by authoring the language master and creating the root pages of language copies.

1.  Create [translation projects](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) to gather the content to translate and to prepare the translation process.

1.  Use the translation projects to [manage the content translation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) process.


When your translation service provider does not provide a connector to integration with AEM, then AEM supports the manual export and import of translated content in XML format.

>[!TIP]
>
> See the *Translation* section in the Best practices guide for best practices around translating content.

## Configure the Translation tab on the DITA map dashboard 

To hide the Translation tab on the DITA map dashboard, perform the following steps:

1.  Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file.
1.  In the configuration file, provide the following \(property\) details to configure the translation tab on the map dashboard:

    |PID|Property Key|Property Value|
    |---|------------|--------------|
    |`com.adobe.fmdita.config.ConfigManager`|`hide.tabs.translation`|Boolean \( true/ false\).

 **Default value**: `true`

|

    >[!NOTE]
    >
    > This configuration is enabled by default and the translation tab is not available on the map dashboard.


## Configure component-based translation workflow 

If the connector for the translation vendor does not support DITA content, then the component-based translation workflow needs to be enabled. Once enabled, the translatable content is sent as asset metadata. However, the connector needs to support asset metadata translation for this workflow to work.

Based on the translation workflow used in your setup, the component-based translation workflow option should be configured. Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure component-based translation workflow:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`|`component.translation`|Boolean:

 -   If you are using human translation, then *Disable* \( `false`\) the **Component-Based Translation Workflow** option.

-   If you are using machine translation, then *Enable \( `true`\)* the **Component-Based Translation Workflow** option.


|

>[!NOTE]
>
> If you are using translation connector, then ensure that you have configured the connector as described in the *[Configuring the Translation Integration Framework](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* topic in AEM documentation.

>[!IMPORTANT]
>
> After setting up the translation configurations, ensure that you set up the appropriate Cloud Configuration on the language folders.

## Configure post-processing of temporary language copies 

When you initiate the translation workflow, the system creates temporary language copies of the source content. You can choose to enable or disable the post-processing operation on these temporary files. In the post-processing operation, the incoming and outgoing references from the files are resolved, the document state is set, along with other operations. If you enable post-processing on these temporary files, the translation process could take longer time to complete. Therefore, it is recommended to keep post-processing option disabled.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure post-processing of temporary language copies:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`|`postprocess.temporary.langcopies`|Boolean:

 -   If you do not want to run the post-processing operation on the temporary files, then *Disable* \( false\) the **Post-process language copies** option.

-   If you want to run the post-processing operation on the temporary files, then *Enable* \( true\) the **Post-process language copies** option.


 **Default value**: false

|

