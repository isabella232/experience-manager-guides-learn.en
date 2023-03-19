# Manage review tasks using the Review Dashboard {#id2056B0Y70X4}

Review management workflow can include a variety of tasks. For example, you may want to add reviewers for a particular topic or extend the deadline for a review. You might also want to mark the review task as complete if you think that all the stakeholders have given their feedback. These tasks can be managed using the Review Dashboard.

Perform the following steps to access and use the Review Dashboard:

>[!NOTE]
>
> You can manage review tasks for only those projects for which you are the Author \(or initiator\). Even if you are a Reviewer or Publisher \(user\), you will not have access on any of the project tasks.

1.  In the **Projects** console, click the review project you want to manage.

    A Project panel with task tiles is displayed.

    ![](images/review-management.png)

1.  Click the three dots in the **Reviews** tile.

    The Review Dashboard is displayed. The dashboard lists all review tasks that you have created.

    ![](images/review-dashboard.png)

    The Review Dashboard displays the details about the review task such as the task name, who started the review, date when the review was started, due date, status, number of new comments that have not been accepted or rejected by the author, and name of reviewers. The tasks are listed in the order of newly created tasks to older tasks.

    >[!NOTE]
>
> If you click on the Review Task link, the topic or map file sent for review is opened.

1.  Select a review task.

    You are shown Edit Properties and [Status](#check-review-status-id199RF0A0UHS) options in the toolbar.

1.  If you click **Edit Properties**, the Task Details page is displayed.

    There are three tabs on the Task Details page– Task, Content, and Reviewers. The following sections explain the various functions available under each tab.


## Task tab 

![](images/review-task-page.png)

You can perform the following actions under the **Task** tab:

-   -   Modify the title of the task in the **Title** field.

-   Add default assignees in the **Assign To** drop-down list. The reviewers you add from here are given access to review all topics that are a part of this review task. You can choose to remove or selectively add more reviewers to specific topics from the [Reviewers tab](#reviewer-tab-id199RF0N0MUI).

-   Update the description of the task in the **Description** field.

-   Modify the **Due Date**. You can prepone or postpone the deadline for the completion of the task.

-   Select the option to restrict users to review only those topics that are assigned to them.

-   Click **Update** to update the modified details.

-   Click **Complete** to mark the review task as complete before the due date. When an individual topic's task is marked as Complete, the review of the selected topic is closed. However, in case of topics shared for review through a DITA map, marking the DITA map task as Complete will close the review of all topics within the map that were shared for review.

-   Click **Duplicate** to create a copy of the review task. The process of creating a duplicate review task is similar to creating a new review task. Once you launch the duplicate task workflow, you are shown the Create Review Task page. You need to provide the new task details as explained in [Send topics for review](review-send-topics-for-review.md#).

    If you have selected a review task created out of a DITA map, then you are shown the topics that are a pert of the map. You can then choose the topics that you want to include in the new review task.

    In case of review task duplicated from one or multiple topics review, then only those topics are shown in the review task list. You can choose to share these topics for review with a different set of reviewers.

-   Click **Close** to go to the Inbox page.

## Content tab 

![](images/review-content-page.png)

You can perform the following actions under the **Content** tab:

-   Change the version of the topic sent for review. You can choose the latest version of the topic, version as on date, version with specific label, or version with a specific baseline \(for a DITA map\).

-   Click **Update** to share the updated version of the topic with the reviewers. The reviewers get an email notification stating that the newer version of topic has been sent for review. The next time a reviewer opens the topic, they see the updated version of the topic.

    >[!NOTE]
>
> In case of an updated version of a topic, the old comments are retained in the newer version as well. Reviewers can also see the differences between the two versions.

-   Click **Complete** to mark the review task as complete before the due date. When an individual topic's task is marked as Complete, the review of the selected topic is closed. However, in case of topics shared for review through a DITA map, marking the DITA map task as Complete will close the review of all topics within the map that were shared for review.

-   Click **Duplicate** to create a new review task using the current task as the base.


## Reviewers tab {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png)

You can perform the following actions under the **Reviewers** tab:

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

## Check the status of a review task {#check-review-status-id199RF0A0UHS}

From the main Review Dashboard page, if you select a review task and click **Status**, the status report of the review task is shown:

![](images/review-status-report.png)

The status report for the review task contains the following details:

-   Name\(s\) of the reviewer to whom the review task is assigned.
-   The Status column indicates the review status. The Status could be one of the following:
    -   **Not Started**: The reviewer has not yet opened the review link.
    -   **In Progress**: The reviewer has opened the review link and is in the process of reviewing the topic.
    -   **Complete**: The reviewer has completed the review by completing the review task assigned to them. The review task is in the AEM notification Inbox for each reviewer.
-   When a reviewer opens a review link and navigates to a particular topic that topic is added to the Topics Reviewed list. This helps authors to determine if the reviewers had opened their respective sections or not. If any comments are given, those are shown in brackets.
-   Total number of comments made on all topics. In case of multiple topics under review, the number of comments for each topic is mentioned \(in brackets\) against the topic name.
-   The date when any topic was last accessed by the reviewer.

**Parent topic:**[Review topics or maps](review.md)

