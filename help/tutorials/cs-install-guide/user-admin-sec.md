---
title: User administration and security
description: Learn how User administration and security work
---
# User administration and security {#id181AED00G5Z}

To access and configure features in the AEM Guides, you need to create users. These users can then be assigned permissions to access all or specific features in the AEM Guides. Learn how to configure and maintain user authorization and also understand the theory behind how authentication and authorization works in AEM.

The following topics in AEM documentation will help you understand the user administration and security-related concepts and features:

-   [AEM users, groups and permissions](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

-   [User Administration and Security](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html)


## User groups created by AEM Guides {#id181TF0K0MHT}

AEM Guides provides three out-of-the-box groups to manage different tasks in a DITA project. These groups are: *Authors*, *Reviewers*, and *Publishers*. Depending upon the group a user is associated with, they are allowed to perform specific tasks. For example, publishing task can be performed only by a publisher, but not by an author or a reviewer. Similarly, an author can create a new topic, and a reviewer can only review a topic.

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

## Additional notes on user groups 

The following list contains some recommendations and points related to user groups and corresponding permissions:

-   If you want a user to start the translation or review workflow, ensure that the user is a member of the *Publishers* and *projects-administrators group*.

-   Users must have the read, create, delete, and modify permissions available on the source and target language folders that they need to work on.

-   If you create a project, you are the owner of the project with *Publishers* permissions. For other users in a project to be able to see their team members, create tasks, or create workflows, they must have read access on `/home/users` and `/home/groups` nodes. One way of giving read access on `/home/users` and `/home/groups` nodes is by giving read access to the `projects-users` group.

-   *Reviewers* can access and add review comments on a topic under review from the Project console or from inbox notification link. Also, this access is only available till the time the review task is open.

-   By default, *Publishers* are granted access and permissions on the following folders in DAM:

    -   `/content/fmdita` –\> Read and Write

    -   `/content/dam/fmdita-outputs` –\> Read and Write

    -   `/content/output/sites` –\> Read and Write

    You must give explicit read and write permissions to your publisher if you are using any other location apart from the default publishing locations mentioned above.

-   All users under *Authors*, *Reviewers*, and *Publishers* groups have read access on all content in DAM.

-   Folder-level permissions must be assigned to users via the user administration page.

-   If you want your users to be able to perform search operations on DAM, then make your users a member of the *dam-users* group.

-   If you want to give admin rights to any user, you can do so by giving them access through AEM standard groups like *administrators*, *projects-administrators*, or OSGI configuration \(Felix console\).

-   To give a user rights to change a document state, make sure that you add the user in the state transition section of the document state profile.

[1](#fnsrc_1) If *Authors* and *Publishers* are invited for a review.[2](#fnsrc_2) Depending on the rights given to the user in the document state profile.
