---
title: Create a DITA project
description: Learn how to Create a DITA project
---

# Create a DITA project {#id1645HA00NM6}

AEM Guides provides a DITA project template that you can use to create and manage your review tasks.

You can create a DITA project and then use it to initiate your reviews. A project lets you define a deadline and control the tasks and time required to complete the review task for which you have created the project.

You can add team members to a project who could then be assigned various roles – Authors, Reviewers, and Publishers.

Once you have created your DITA project, you can initiate your review from the Web Editor or the Assets UI. For more details, see [Send topics for review](review-send-topics-for-review.md#).

Similarly, whenever an author initiates any review workflow the selected members of the project get an email notification. To configure email notifications, see *Customize email templates* in Install and configure Adobe Experience Manager Guides as a Cloud Service.

Perform the following steps to create a DITA project:

1.  Open Projects console.

    You can also access the Projects console using the following URL:

    ```http    
    http://<server name>:<port>/projects.html
    ```

1.  Click **Create** \> **Project** to launch the Create Project wizard.

    ![](images/project-console-63.png)

1.  On the Create Project page, select the **DITA Project** template and click **Next**.

1.  On the Project Properties page, enter the following details:

    Information in the **Basic** tab:

    ![](images/create-project.png)

    -   Enter your project's **Title**, **Description**, and **Due Date**.

    -   You can, optionally, choose a thumbnail for the project.

    -   By default, you are made the owner of the project. To add more users to this project:

    1.  Enter or choose a user from the **User** drop-down list.

    1.  Choose a user type - Authors, Reviewers, or Publishers.

        >[!NOTE]
        >
        >You will see other user types in this drop-down list, but for a DITA project you should only choose from Authors, Reviewers, or Publishers user type. Even if you add a user of a different type, that user will not be able to access any DITA-specific features available in AEM Guides.

    1.  Click **Add**.

        >[!NOTE]
        >
        >If you are using AEM Guides version 3.5 or earlier, you are shown an option to select a DITA map file to resolve key references for topic editing, preview and review workflows. In 3.6 and later versions, you can set the root map through the Web Editor. For more information, see the [User Preferences](web-editor-features.md#id2087G0P40SB) in the Web Editor. Another way of setting the root map is by configuring it at the global or folder-level profiles. For more details, see *Configure global or folder-level profiles* in the Installation and Configuration Guide.

    Information in the **Advanced** tab:

    -   Enter a name for the project. This name is used to create the URL for this project.

1.  Click **Create**.

    The Project Created dialog appears.

1.  Click **Open** to open your project page.


**Parent topic:**[Review topics or maps](review.md)

