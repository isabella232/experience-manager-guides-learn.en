---
title: Send topics for review
description: Learn how to Send topics for review
---

# Send topics for review {#id199RD0S035Z}

The review workflow creates a multi-reviewer environment wherein the initiator specifies a list of topics for review, add multiple reviewers, and assigns a timeline for the review task. AEM Guides allows users belonging to the Authors and Publishers groups to initiate a review.

As the review workflow is project-specific, the initiator of review must be a part of the project team or have rights to create a project. At the time of creating a project, you define the team members for the project and assign them various roles or groups. For more information about projects, see [Create a DITA project](authoring-create-dita-project.md#).

You can create a review task from:

-   **Web Editor**: Allows you to send an individual topic or DITA map for review. Note that the workflow for creating a review task is common across the Web Editor and Assets UI. Only the method of launching the review workflow differs. For information about launching the review workflow from the Web Editor, see the [Create Review Task](web-editor-features.md#id215OCJ00JXA) feature in the Web Editor.

-   **Assets UI**: Allows you to send one or multiple topics and DITA map for review. Sharing documents for review from Assets UI workflow is covered under this topic.


From the Assets UI, there are two ways in which an Author/Publisher can create a review task:

-   Send one or more topics for review
-   Send multiple topics from a DITA map for review

## Send one or more topics for review {#id1721E600FY4}

>[!IMPORTANT]
>
> Before you create a review task, ensure that you have created a project and added reviewers to that project.

To create a review task and send topics for review, perform the following steps:

>[!NOTE]
>
> You can create a review task only if you are an author or publisher in a DITA project.

1.  Navigate to the required folder in the Assets UI.

1.  Click the Select icon in the quick action and select the topics you want to send for review.

    ![](images/select-asset-62.png)

1.  In the toolbar, click **Create Review Task**. The review task creation page is displayed.

    >[!NOTE]
    >
    > You can create a review task for only those topics that have a revision. In case the selected topic does not have a revision, you will be shown a prompt.

    ![](images/create-review-task-023.png)

1.  Enter a **Title** for the task and select a DITA **Project** from the drop-down list.

1.  In the **Assign To** drop-down field, select the reviewers to whom you want to send the topics for review.

    You can assign a review task to individual users of the project or to user groups. Note that you can assign a review task to individual users only when you are a part of the project's administrator group, else you will only see the user groups in the Assign To field.

    >[!NOTE]
    >
    > Review workflow is project-specific. When you create projects, you add the team members to the project and assign them to groups. So when you select the project here, you get to choose the members who are a part of that project. For more information about projects, see [Create a DITA project](authoring-create-dita-project.md#).

1.  Enter a **Description** for the task.

    This description is used as the body of the notification email sent to the reviewers.

1.  Select the **Due Date** and time to mark the deadline for the review.

    >[!NOTE]
    >
    > On reaching the deadline, an email is sent to the initiator notifying that the review task has completed. The initiator can extend the deadline of the review task from the [Review Dashboard](review-manage-tasks-review-dashboard.md#).

1.  Select the root map from the **Rootmap path**. This rootmap is used to resolve all the key references and glossary terms used in the review content. If you do not select the rootmap then the key references or glossary terms associated with the DITA topic, are not resolved before sending the topic for review.

    If you are creating the review for a DITA map, then by default **Rootmap path** is set to that map's path. If you are creating the review for a single or multiple topics, then by default the **Rootmap path** is set to the map defined in the User Preferences.

    >[!NOTE]
    >
    > The selected root map takes the highest precedence to resolve key references. For more details, see [Resolve key references](map-editor-other-features.md#id176GD01H05Z).

1.  As you can assign different reviewers to different topics, **Allow Assignees to Review Any Topic** option controls whether reviewers can review all topics in a review task or only those topics that they are assigned to review.

    If you want to allow all reviewers to review any topic in the review task, select **Allow Assignees to Review Any Topic**.

    If you do not select this option then reviewers added in the **Assign To** field will have access to review only those topics that are assigned to them.

1. Click **Next**.

    The Content page is displayed.

    ![](images/content_page_review.png)

1. On the Content page, select a version of the topic that you want to share for review.

    You can use one of the following methods to select a version:

    -   *\(Default\)* Choose the option **Their Latest Version** to select the last saved revision of the topics.
    -   Choose the **Version On** option and specify the date and time to select a version as on the specified date and time. If there is no version of topic available on the specified date, then a version available immediately after the specified date and time is selected.
    -   Choose the **Select a Label** option and select a label from the drop-down list.
1. After making your selection for choosing a version, click **Apply**.

    The version based on the selected option is chosen for the topics.

    >[!NOTE]
    >
    > You can also manually select the desired version from the **Version** drop-down list of each topic.

1. Click **Next**.

    The Reviewers page is displayed wherein you can add or remove reviewers. By default, the reviewers added in the Assign To field are auto-added to each topic selected for the review.

    ![](images/add-reviewers-topics.png)

1. On the Reviewers page, you can add or remove reviewers. The following operations are available on the Reviewers page:

    -   **Select All**: Selects all topics in the topic list. You can easily perform a batch operation after selecting all topics.
    -   **Clear Selection**: Deselects the topics selected in the topics list.

        >[!NOTE]
        >
        > You can also individually select or deselect a topic by clicking on the checkbox next to the topic.

    -   **Add**: Displays the Add Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to add as a reviewer to the selected topics.
    -   **Remove**: Displays the Remove Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to remove as reviewer from the selected topics.

        >[!NOTE]
        >
        > You can also remove a review from a topic by clicking the cross sign in the reviewer's box.

    -   **Re-Assign**: Displays the Re-Assign Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to assign the review task to. This removes all existing reviewers from the selected topics and assigns the newly selected reviewers to those topics.
    -   **Export**: Allows you to export the review task details in a CSV file. The file contains details such as the path and title of the topic, name of reviewer, and version of topics sent for review.
    -   **Edit Reviewers**: Clicking the ![](images/edit_pencil_icon.svg)icon in the topic list displays the Edit Reviewers dialog. You can add or remove reviewers for the selected topic from this dialog.
1. Click **Create** to create the review task.

    A confirmation message is displayed when the review task is created successfully. The [Document state](web-editor-document-states.md#) for the topics sent for review is set to In-Review.

    >[!NOTE]
    >
    > You can also click Notifications bell at the top right of the screen and confirm that the review task has been created successfully. In the Notifications panel, you will find one notification each for the reviewers who were a part of the review task and one notification for the initiator of the review.


An email is sent to all reviewers, notifying that they have been assigned a topic or multiple topics for review. The email contains a direct link that they can click and access the topic in a browser window.

In case multiple topics are assigned, the reviewers can view and select them in a drop-down list of topics in the web browser.

## Send multiple topics for review from a DITA map 

A DITA map is a logical organization of topics within a book. When you send an individual topic for review, the reviewer does not get any information about the location of that topic in the book. If a reviewer has information about the exact location of the topic being reviewed, the reviewer gets a better context of the topic being reviewed.

AEM Guides allows you to send one or more topics in a DITA map for review at the same time. The reviewer gets to see the complete map file along with topics that have been shared for review. This makes it easier for the reviewer to get a context of the topic in the map or book file.

You can share the same DITA map in for review in multiple review tasks. For example, if in a DITA map there are topic A, B, C, D and E. In one review task you can share A, B, and C for review and in another review task you can send topics C, D and E for review. The review process allows for sharing the same topic and map file in multiple review tasks. For the common topic in multiple review tasks, the comments given in one review task do not overwrite or merge with the comments in the other review tasks.

>[!IMPORTANT]
>
> In case a topic of a map file has been shared in multiple review tasks, their status would show In-Review until all review tasks have completed.

To send one or multiple topics along with the map file for review, perform the following steps:

>[!IMPORTANT]
>
> Once you initiate a review through a map file, you must not change the structure of the map file by adding new topics or removing existing topics.

1.  Navigate to the required folder in the Assets UI.

    >[!NOTE]
    >
    > Make sure the view of the console is set to either card view or list view.

1.  Select the map from where you want to send the topics for review.

1.  In the toolbar, click **Create Review Task**. The review task creation page is displayed.

1.  Enter a **Title** for the task and select a DITA **Project** from the drop-down list.

    >[!NOTE]
    >
    > You can create a review task for only those topics that have a revision. In case your map contains topics that do not have a revision, then you are shown a prompt with a list of such files. Files without a revision are excluded from the review task.

1.  In the **Assign To** drop-down field, select the reviewers to whom you want to send the topics for review.

    You can assign a review task to individual users of the project or to user groups. Note that you can assign a review task to individual users only when you are a part of the project's administrator group, else you will only see the user groups in the Assign To field.

    >[!NOTE]
    >
    > Review workflow is project specific. When you create projects, you add the team members to the project and assign them to groups. So when you select the project here, you get to choose the members who are a part of that project. For more information about projects, see [Create a DITA project](authoring-create-dita-project.md#).

1.  Enter a **Description** for the task.

    This description is used as the body of the notification email sent to the reviewers.

1.  Select the **Due Date** and time to mark the deadline for the review.

    >[!NOTE]
    >
    > On reaching the deadline, an email is sent to the initiator notifying that the review task has completed. The initiator can extend the deadline of the review task from the [Review Dashboard](review-manage-tasks-review-dashboard.md#).

1.  As you can assign different reviewers to different topics, **Allow Assignees to Review Any Topic** option controls whether reviewers can review all topics in a review task or only those topics that they are assigned to review.

    If you want to allow all reviewers to review any topic in the review task, select **Allow Assignees to Review Any Topic**.

    If you do not select this option then reviewers added in the **Assign To** field will have access to review only those topics that are assigned to them.

1.  Click **Next**.

    The Content page is displayed with all topics referenced from the map file. If your DITA map contains nested maps, then topics from the nested maps are also listed here.

    ![](images/content-page-map-review.png)

1. On the Content page, select a version of the topic that you want to share for review.

    You can use one of the following methods to select a version:

    -   *\(Default\)* Choose the option **Their Latest Version** to select the last saved revision of the topics.
    -   Choose the **Version On** option and specific the date and time to select a version as per the date and time. If there is no version of topic available on the specified date, then a version available immediately after the specified date and time is selected.
    -   Choose the **Select a Label** option and select a label from the drop-down list. All topics containing the selected label are selected in the **Version** drop-down list.
    -   Choose the **Select a Baseline** option and select a baseline from the drop-down list. All topic versions that are a part of the selected baseline are selected in the **Version** drop-down list.
1. After making your selection for choosing a version, click **Apply**.

    The version based on the selected option is chosen for the topics.

    >[!NOTE]
    >
    > You can also manually select the desired version from the **Version** drop-down list of each topic.

1. Click **Next**.

    The Reviewers page is displayed wherein you can add or remove reviewers. By default, the reviewers added in the Assign To field are auto-added to each topic selected for the review.

1. On the Reviewers page, you can add or remove reviewers. The following operations are available on the Reviewers page:

    -   **Select All**: Selects all topics in the topic list. You can easily perform a batch operation after selecting all topics.
    -   **Clear Selection**: Deselects the topics selected in the topics list.

        >[!NOTE]
        >
        > You can also individually select or deselect a topic by clicking on the checkbox next to the topic.

    -   **Add**: Displays the Add Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to add as a reviewer to the selected topics.
    -   **Remove**: Displays the Remove Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to remove as reviewer from the selected topics.
    -   **Re-Assign**: Displays the Re-Assign Reviewers dialog. You can type the name of a reviewer or user role \(or group\) that you want to assign the review task to. This removes all existing reviewers from the selected topics and assigns the newly selected reviewers to those topics.
    -   **Export**: Allows you to export the review task details in a CSV file. The file contains details such as the path and title of the topic, name of reviewer, and version of topics sent for review.
    -   **Edit Reviewers**: Clicking the ![](images/edit_pencil_icon.svg)icon in the topic list displays the Edit Reviewers dialog. You can add or remove reviewers for the selected topic from this dialog.
    >[!IMPORTANT]
    >
    > You must assign at least one reviewer to create the review task.

1. Click **Create** to create the review task.

    A confirmation message is displayed when the review task is created successfully. The [Document state](web-editor-document-states.md#) for the topics sent for review is set to In-Review.

    >[!NOTE]
    >
    > You can also click Notifications panel at the top right of the interface and confirm that the task has been created successfully. In the Notifications panel, you will find one notification each for the reviews who were a part of the review task and one notification for the initiator of the review.

    >[!IMPORTANT]
    >
    > Once you have initiated a review, you must not move or delete the DITA map or topics to a different location. Doing so will result in a break in the review process.


An email is sent to all the reviewers, notifying that they have been assigned topics for review. The email contains a direct link that they can click and access the topic in a browser window. The topics along with the DITA map are opened in the review mode.

**Parent topic:**[Review topics or maps](review.md)

