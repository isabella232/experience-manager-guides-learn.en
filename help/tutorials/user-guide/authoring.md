---
title: Manage content
description: Learn how to Manage content
exl-id: d2fa31a7-a8ce-4d17-bd4e-0f51ea751dca
---
# Manage content {#id164JBG0M0T1}

Before you start with the actual content creation, you must familiarize yourself with some basic concepts of content management in AEM Guides. Then, start with creating different user groups and organizing your assets.

## Key concepts 

Some key concepts of content management in AEM are as follows:

**Asset management**

AEM Guides uses AEM's digital asset management \(DAM\) to manage your DITA files. The files that you upload or check into the DAM are stored as digital assets. You can manage and edit your assets in AEM Assets. For more information about asset management, see [Manage assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Link management**

Move or rename files or change folder structure in the content repository, without worrying about broken references. All references to and from the impacted content are automatically updated. Get warnings when deleting content which is referenced from elsewhere, to prevent unintentional breakages.

**Managing versions**

AEM Guides provides version management for your digital assets. You can easily enable this functionality from a DITA authoring application of choice. Allowing your writers to perform the standard version control functions such as check-in and check-out.

For more information about creating versions or reverting to a specific version, see [Branch, revert, and subsequent versioning](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA handling**

While AEM Guides maintains the structure of your DITA files, it also enables AEM to natively handle DITA using element mapping to map the DITA elements to AEM components. The native DITA handling is used in features such as topic preview, AEM Sites publishing, and the review workflows.

## Identify your role and permissions {#id181TF0K0MHT}

AEM Guides provides three out-of-the-box groups. These groups are: *Authors*, *Reviewers*, and *Publishers*. Depending upon the group you are associated with, you have permissions to perform specific tasks as mentioned in the table given below. For example, publishing task can be performed only by a publisher, but not by an author or a reviewer. Similarly, an author can create a new topic, and a reviewer can only review a topic.

>[!TIP]
>
> See the *Permissions*section in the Best practices guide for best practices around setting user permissions.

The following table lists various tasks and the groups that can perform those tasks:

|Task|Authors|Reviewers|Publishers|
|----|-------|---------|----------|
|Create DITA Topic|Yes| |Yes|
|Create DITA Map|Yes| |Yes|
|Map Collections|Yes| |Yes|
|Create Review Task|Yes| |Yes|
|Review Topic[1](#fntarg_1)|Yes|Yes|Yes|
|Key Resolution|Yes| |Yes|
|Check-out/Check-in|Yes| |Yes|
|Edit Topic|Yes| |Yes|
|Move Topic|Yes| |Yes|
|Edit Topic Properties|Yes| |Yes|
|Copy|Yes| |Yes|
|Delete|Yes| |Yes|
|Share|Yes| |Yes|
|**Document state**|
|Create/edit document state profile| | |Yes|
|Change document state[2](#fntarg_2)|Yes|Yes|Yes|
|**Features available in DITA map console \(Output Presets tab\)**|
|Generate| | |Yes|
|Edit| | |Yes|
|Duplicate| | |Yes|
|Create| | |Yes|
|Delete Preset| | |Yes|
|**Features available in DITA map console \(Outputs tab\)**|
|View generated output|Yes| |Yes|
|**Features available in DITA map console \(Topics tab\)**|
|Create Review Task|Yes| |Yes|
|Edit|Yes| |Yes|
|**Features available in DITA map console \(Baselines tab\)**|
|Create| | |Yes|
|Edit| | |Yes|
|Duplicate| | |Yes|
|Remove| | |Yes|
|DITA map console \(Reports tab\)|Yes| |Yes|
|**Features available in DITA map console \(Condition Presets\)**|
|Create/edit condition preset| | |Yes|

[1](#fnsrc_1) If *Authors* and *Publishers* are invited for a review.

[2](#fnsrc_2) Depending on the rights given to the user in the document state profile.

## Pre-requisites to content authoring 

**Work with global or folder-level profiles**

In an enterprise, different groups or products may use different authoring templates, output templates, conditional attribute profiles \(or subject schemes\), and Web Editor configurations. Configuring these only at an enterprise \(or global\) level can make authors experience difficult, as they will see templates or profiles that are not relevant to them.

AEM Guides allows you to configure authoring \(topic or map\) templates, output templates, conditional attribute, and Web Editor configurations at an enterprise \(global\) level as well as at a folder level. This way, you can segregate the configurations for different departments or products in your enterprise.

Also, you can delegate the folder-specific configurations to a department or product administrators to decentralize the administration.

For details on setting up global and folder-level profiles, see *Configure global or folder-level profiles* in Install and configure Adobe Experience Manager Guides as a Cloud Service.
