---
title: Upload files
description: Learn how to upload your files to the AEM repository and handle errors. Know assets console user interface, AEM desktop app, asset bulk ingestor, and use FrameMaker for bulk upload.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
---
# Upload files {#id176FF000JUI}

Most likely you would have a repository of existing DITA content that you would like to use with AEM Guides. For such existing content, you can use any of the following approaches to bulk upload your content into AEM repository:

>[!IMPORTANT]
>
> See [Add digital assets to Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) for detailed information in the supported content upload methods in AEM.

## Assets Console user interface 

You can select content on your desktop and drag on the AEM user interface \(web browser\) to the destination folder. For more details, see [Upload assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) in AEM documentation.

## AEM desktop app 

Use AEM desktop app if you are a creative professional, and want to manage the assets on your local desktop. You can open and edit these assets with your desktop applications. You can also maintain versions and share your files with other users. For more details, see [AEM desktop app](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Asset bulk ingestor 

If you have large-scale migrations and occasional bulk ingestions, use Asset bulk ingestor to upload your content. Using this tool, you can upload bulk content from supported datastores like Azure or S3. For more details, see [Asset bulk ingestor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Use FrameMaker for bulk upload 

Adobe FrameMaker comes with a powerful AEM connector that allows you to easily upload your existing DITA and other FrameMaker documents \(`.book` and `.fm`\) into AEM. You can use various file upload functionalities such as uploading a single file, uploading a complete folder with or without dependencies \(like content references, cross-references, and graphics\).

For more details about using bulk upload feature in FrameMaker, see the section *Create a CRX folder and upload files* in FrameMaker User Guide.

## Error handling while uploading content {#id201MI0I04Y4}

In case of any failure to upload one or more files, a prompt is displayed at the end of the upload process with a list of files that failed to upload:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

For more details about how the various file uploading scenarios, see [Upload DITA content](authoring-file-management.md#).

 In case you use a tool like AEM desktop app or Asset bulk ingestor, then the action to perform on a duplicate file is controlled by a setting in the AEM server. Contact your system administrator to know about this configuration.

**Parent topic:**[Manage content](authoring.md)
