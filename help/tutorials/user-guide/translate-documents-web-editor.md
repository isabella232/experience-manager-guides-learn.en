---
title: Translate documents from the Web Editor
description: Learn how to Translate documents from the Web Editor
exl-id: 02fc2b51-5b9a-4ad6-9e2e-726ab7602514
---
# Translate documents from the Web Editor {#id21BKF0Z0YZF}

>[!TIP]
>
> It is recommended to use this Translation feature from the Web Editor if you have upgraded to AEM Guides as a Cloud Service February 2022 release or later.

AEM Guides comes with a powerful feature in the Web Editor that enables you to translate your content into multiple languages. You can create a new translation project and later add the translation jobs to the existing translation project. You can also create a multi-lingual translation project which includes translation jobs for all the selected languages.

>[!NOTE]
>
> Your administrator can configure the Manage tab \(used for translation\) in the Web Editor. For more details, see *Configure the translation feature in the Web Editor* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

## Before you begin 

Before performing steps in this procedure, ensure that you have created the required language root and target folders

1.  Create a root folder to store your source content. The root folder must be created with the language name \(such as English\) or language code \(en\).
1.  Create the destination folders to which you want to translate your content. For example, if you want to translate your content into German or French, then you must create folder named as -de \(for German\) or -fr \(for French\).

>[!NOTE]
>
> The root folder and the destination folders must be created at the same level.

## Create a translation project 

1.  In the Repository panel, open the DITA map file in map view.
1.  Click the **Manage** tab. The Translation panel displays the hyperlinked title of the DITA map along with the **Languages** list.
1.  From the **Languages** list, select the locale to which you want to translate your project. You can select **All** to translate your project into all the available languages.

    >[!NOTE]
    >
    > The list contains the language folders along with their language codes. For example, French \(fr\) and German \(de\).

    >[!IMPORTANT]
    >
    > Language shows only those languages for which a language folder is created parallel to the source language. A language folder created at any other level, such as one level down from the source language folder is also not shown. Ensure that you create all your target language folders at the same level as your source language folder.

    ![](images/translation-languages.png){width="350" align="left"}

1.  You can also use the following options:

    **Use Baseline:** You can select a baseline to translate your project. Click Use Baseline and choose a baseline created on the map. All files that are a part of the selected Baseline are shown in the Translation page. Once your content is translated, you can export the translated Baseline. For more details about exporting the translated Baseline, see [Export translated Baseline](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

    **Use Latest Version as on**: Choose to filter the version of topics based on their creation date and time. When you select a date and time only the latest version of the files created on or before the selected date and time are shown.

1.  Click **Apply**. A list with details of topics and associated assets is shown.
1.  Select the topics that you want to send for translation.

    You can also use the following topic filtering options:

    -   **Title**: Title of the source file
    -   **File Name**: Name of the source file
    -   **File Type**: Type of the source file. The available options are Map, Topic, and Image.
    -   **Reference Type**: Direct or Indirect references
    -   **Version**: Version number of the source file
    -   **Version Label**: Label for the selected version of the source file
    -   **Target Version**: Version number of the target file
    -   **Document State**: State of the source file. The available options are Draft, In-Review, and Reviewed.
    -   **Target Language**: The language to which you want to translate the source file
    -   **Translation Status**: The available options are: Out of Sync, Missing Copy, In Progress, and In Sync.
    -   **Target Label**: Label for the selected version of the target file
1.  Click **Send for Translation** on the top right corner.

    ![](images/translation-send.png){width="800" align="left"}

1.  From the dropdown, select **Create a New Translation Project**.

    ![](images/translation-project-types.png){width="350" align="left"}

    Besides a new translation project, you also can select from the following options:

    -   You can choose to **Create a structure** only for the translation project.
    -  You can choose to **Create a new XLIFF translation project** to convert the XML content into the XML Localization Interchange File Format (XLIFF). XLIFF is an open XML-based format that is used to standardize the data transfer between various tools used in the content translation process. 
    In an XLIFF project, the content is exported to the industry standard XLIFF format, which can be provided to Translation vendors. XLIFF format empowers potential reuse of segments that you have already translated during the translation phase.  
    After the XLIFF content is translated, it can be imported into AEM Guides, creating a translated version of the original DITA project. 

        >[!Note]
        >
        > XLIFF export only works with human translation configuration. 

    -   You can select **Create a new multi-lingual translation project** which will include translation jobs for all languages that you have selected for translation. For example, if you have selected French, German, and Spanish it will create a project which contains translation jobs for all three languages.
    -   If you already have a translation project, you can add topics to that project. Select Add to **Existing Translation Project** option from the Project list and choose a project from the Existing Translation Project list. You can sort these projects by most recent, ascending, or descending order.

        >[!NOTE]
        >
        > If your existing project is a scoping project, it has '\(Scoping\)' appended in its name.

    -   If you need to create the scope for a project to be translated, you can select **Create a new scoping translation project**. This will not send the copies for translation and the original translation status of the files is maintained. There is no impact on the destination language copy of the referred topics which are sent for scoping.
1.  In the **Project Title** field, enter a title for the project.
1. Click **Create** to create a new translation project.

    A new translation project is created with the selected version of the topics. At this time, a pop-up message is displayed confirming that the translation project has been created. Once all target language copies are available in the translation project, you get a notification in the Inbox. Once the target language copies are available in the translation project, you can then go ahead and start the translation job. For details see, [Start the translation job](translation-first-time.md#id225IK030OE8).

    >[!NOTE]
    >
    > If you reject the translation for one or more topics in a translation job, the **In Progress** translation status of all the rejected topics reverts to their original status. The status of the referred topics is checked and reverted according to the latest translation state. Also, the translation files created in the destination project are not deleted even if the translation is rejected for them.

## Add the translation rules  

AEM Guides allows your administrators to configure the translation rules. The SRX (Segmentation Rules eXchange) format is a standard for exchanging segmentation rules between different users and different translation environments. You can create a folder and add your custom SRX files to it.  

SRX files should be named as `<language-code>.srx`. For example, en-US, or ar-AE.  

>[Note]
>The title is not case-sensitive, so you can have 'en-US' or 'en-us' or 'EN-us'. Also, AEM guides can resolve '-' (hyphen) or '_' (underscore). So, you can have 'en-US' or 'en_US'. 

Also, you can put these files inside any folder under AEM assets root that is `./content/dam`. 

 

Once you've created the folder which contains the SRX files, you can add the folder path in the Translation SRX location configuration inside your folder profile.  

It is recommended that for a better performance you should keep only SRX files in the folder that is configured in the folder profile. 

 
AEM Guides picks the SRX rules according to the source language of the translation project. It looks for a custom SRX file for a language, and if you do not define a custom SRX file, then it picks the rules as per the out of the box translation rules. 


For details on setting up global and folder-level profiles, see *Configure authoring templates* section in Install and configure Adobe Experience Manager Guides as a Cloud Service. 

## Pass the version label to the target version 

AEM Guides allows you to pass the label of the source file to the target file. This will help you easily identify the source version for the translated file.

To add the source version label in the target copy, your system administrator must select the option **Propagate source version labels to the target version** under the **Translation** tab in **Editor Settings**.

For example, if you have some source files with the version label `Release 1.0` applied to them, then you can also pass on the source label \(`Release 1.0`\) to the translated file.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> The source label is only attached to one target version. If you move the source label to another version, it is automatically reflected in the latest target label.

## View version difference for Out of Sync files  

AEM Guides provides the feature to check the differences between the selected version and the last translated source version of the topics. You can choose to translate the **Out of Sync** files based on the changes made.

![](images/translation-version-diff.png){width="800" align="left"}

Select the **Show difference**icon \(![](images/show-difference-icon.svg)\) for a topic to see the differences between the last translated version and the current version of the selected file.

>[!NOTE]
>
> **Show difference** icon \(![](images/show-difference-icon.svg)\) appears only for DITA files that have the translation status as **Out of Sync**.

The **Version Difference** dialog appears. It shows the **Last translated version** and the **Selected version** number on the left. The preview window displays the differences between the last translated version and the selected version of the topic.

![](images/version-diff.png){width="650" align="left"}

## Dismiss out of sync assets 

If you make changes in some of the assets, then those assets become Out of Sync. You can either re-translate the modified assets or choose to dismiss Out of Sync status. For example, if you have made some very minor changes which really don't need a translation you can mark their status to In Sync.

To dismiss the Out of Sync status, perform the following steps:

1.  Select the out of sync assets for which you want to change the status.
1.  Select the **Mark In Sync** button \(![](images/translation-mark-in-sync-icon.svg)\) on top. The **Mark In Sync** dialog appears.

    ![](images/translation-mark-in-sync.png){width="550" align="left"}

1.  Click **Force Sync**. It sets the status to In sync for the selected Out of sync assets.

>[!NOTE]
>
> **Mark In Sync** button \(![](images/translation-mark-in-sync-icon.svg)\) appears only for assets that have the translation status as Out of Sync.

## View In Progress translation projects for a map or topic 

Some of the references on your translation dashboard might be in progress status. These references have a **In Progress** link under **Translation Status** column. When you click the link, the **In Progress Projects** dialog opens. In the dialog, you can see the list of all In Progress translation projects \(along with the target language\) which contain the selected reference.

>[!NOTE]
>
> You can see the In Progress link for the translated projects created in AEM Guides as a Cloud Service February 2023 release or later.

Click the name of the reference in the dialog to open it in preview mode. You can also click the translation project to start the translation.

![](images/translation-in-progress.png){width="550" align="left"}

**Parent topic:**[Work with the Web Editor](web-editor.md)
