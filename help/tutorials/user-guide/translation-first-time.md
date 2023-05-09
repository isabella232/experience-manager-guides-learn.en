---
title: Best practices for content translation
description: Learn how to Best practices for content translation
exl-id: 4eff0f27-b3d1-4c6e-af88-bcb3f6d96990
---
# Best practices for content translation {#id1678G0S702F}

Consider the following point for translating content:

-   The folder and file names must comply with the file naming standards such as—there should be no spaces, apostrophe, braces, equals sign, special or non-ASCII characters.

-   If you translate content in different languages, you must create folders corresponding to each language. Each of these language folders will contain the content corresponding to that language. For example, you can create folders using the language designator like `de` for German, `fr` for French, and so on. Or, you can create folders using the language and region designators like `fr-FR` for French as used in France or `fr-CA` for French as used in Canada.
-   The target language should also have the actual locales selected as per the target language folders on their instance.
-   The cloud configuration should be same as that of the source folder and there should be only one cloud configuration in one folder. You can create multiple folders under /conf, if you want to use multiple translation connectors.
-   A folder should not have more than 1000 files in it.
-   Ensure that the user tasked with initiating the translation process has Read, Modify, Create, and Delete permissions on the source and target language folders.
-   As translating content requires creation of a translation project, the user must have access to create project in AEM.
-   If you want to use Conditional Presets with your map, you must create them before initiating the translation process. As Conditional Presets are also bundled in the translated version of the map, creating the presets before initiating the translation process ensure that they are available in the translated version.
-   Content translation process must be started from DITA map console and not the AEM Assets UI.
-   The Component-Based DITA Translation Workflow must not be used if you are translating content via human translation. However, this option must be used for machine translation.
-   The globally used content and media that don't require localization, should be kept out of the language copies.
-   All the common content that has to be localized, should be kept in a common folder under the language folder.

The following illustration shows an example of a folder structure in AEM when you have globally used content and three language copies.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configure translation service 

Perform the following steps to configure the human or machine translation service to use:

1.  In the Assets UI, select the source language folder.

1.  Open the folder properties, and go to **Cloud Services** tab.

1.  In the **Cloud Services** tab, configure the translation service that you want to use.

    You can configure machine-based or human translation.

    Ensure that there is only one configuration for translation connector in one folder. Multiple folders can be created under /conf, if there are multiple translation connectors. The source language folder must have a cloud configuration selected before starting the translation process.

    >[!NOTE]
    >
    > See [Configuring the Translation Integration Framework](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) in AEM documentation for details on integrating with third-party translation services.

1.  Click **Save & Close** to save the updated folder properties.


>[!TIP]
>
> See the *Translation* section in the Best practices guide for the best practices around translating content.

## Create a new translation project 

Perform the following steps to create a translation project:

>[!NOTE]
>
> Before performing steps in this procedure, ensure that you have created the required language root and target folders as described in the [Best practices for content translation](#id1678G0S702F).

1.  In the Assets UI, click on the DITA map file.

1.  Click the **Translation** tab.

1.  From the **Target Languages** list, select the locale to which you want to translate your project and click **Done**.

    A Summary and Details of topics and associated assets is shown.

    >[!IMPORTANT]
    >
    > The **Target Languages** show only those languages for which a language folder is created parallel to the source language. A language folder created at any other level, such as one level down from the source language folder is also not shown. Ensure that you create all your target language folders at the same level as your source language folder.

1.  Select the topics that you want to send for translation.

    You can also use the following topic filtering options:

    >[!NOTE]
    >
    > After applying the required filter, click **Done** in the Filter panel to filter topics based on your selection.

    -   **Translation Status**: Choose to filter topics based on their translation status. The available options are: Out of Sync, Missing Copy, In Progress, and In Sync.
    -   **Search**: Enter one or multiple terms to search in the topic titles.
    -   **Source Type**: Choose to filter topics based on their file types. The available options are: All, DITA, DITA Map, Resource.
    -   **Source Version Modified After**: Choose to filter topic based on their modification date and time. All topics modified after the specified date and time are shown in the list.
    -   **Baseline**: Click Use Baseline and choose a baseline created on the map. All files that are a part of the selected Baseline are shown in the Translation page. You can choose the desired files from the baseline and proceed with the translation process. Once your content is translated, you can export the translated Baseline. For more details about exporting the translated Baseline, see [Export translated Baseline](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1.  Click **Create/Update Language Copies** at the bottom of the Filter panel.

1.  From the **Project** list, select **Create a New Translation Project**.

    >[!NOTE]
    >
    > If you already have a translation project, you can add topics to that project. Select **Add to Existing Translation Project** option from the **Project** list and choose a project from the **Existing Translation Project** list.

1.  In the **Project Title** field, enter a title for the project.

1.  Select the **Include DITA Map** option to send the map for translation.
1.  Click **Start** to create a new translation project.

    A new translation project is created with the selected version of the topics. At this time, a pop-up message is displayed confirming that the translation project has been created. Once all target language copies are available in the translation project, you get a notification in the Inbox. Once the target language copies area available in the translation project, you can then go ahead and start the translation job.

    ![](images/status-translation-uuid.png){width="800" align="left"}


The Translation tab has following sections:

-   **Summary**: Shows the number of referenced topics and source language along with its code.
-   **Details**: Shows the topic title, type of topic, language code of the topic, source language, version of the source topic, label added to the topic, and translation status.




## Start the translation job {#id225IK030OE8}

Perform the following steps to start the translation job:

1.  In the **Projects** console, navigate to the project folder you created for localization.

1.  Click the localization project to open the details page.

1.  Click the arrow on the **Translation Job** tile, and select **Start** from the list to start the translation workflow.

    >[!NOTE]
    >
    > If you are using Human translation service, then you need to export the content for translation. Once you have the translated content, then you need to import it back into the translation project.

1.  To view the status of the translation job, click the ellipsis at the bottom of the **Translation Job** tile.


After the translation completes, the status of the translation job changes to *Ready to Review*. To complete the translation process, you need to accept the translated copy and asset metadata from the Translation Job tile in the Project console.

>[!NOTE]
>
> If you reject the translation for one or more topics in a translation job, the **In Progress** translation status of all the rejected topics reverts to their original status. The status of the referred topics is checked and reverted according to the latest translation state. Also, the translation files created in the destination project are not deleted even if the translation is rejected for them.

**Parent topic:**[Translate content](translation.md)
