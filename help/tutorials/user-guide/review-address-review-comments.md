---
title: Address review comments
description: Learn how to Address review comments
exl-id: 04f6114d-601f-4e92-a303-18a6dd309a49
---
# Address review comments {#id2056B0X0KBI}

As an author, you can address comments in a topic using the Web Editor. The following sections describe ways of editing comments in the Web Editor.

An author can address comments in a document from the Web Editor. Visual indicators are provided indicating whether comments that were inserted \(text\), deleted or highlighted. Also the type of comment is mentioned at the top of every comment entry.

>[!NOTE]
>
> While addressing review comments \(for an active review document\), ensure that you—do not open the in-review topic in multiple tabs with full tags view enabled, do not switch between the Author and Source view modes.

![](images/comments-page-web-editor_cs.png){width="650" align="left"}

In the Web Editor mode, the right panel contains the Review and Tracked Changes icons. The Review panel shows all comments made in your document by reviewers. For more details, view the **Review** panel ![](images/active-review-tasklist-icon.svg) feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. The **Tracked Changes** panel shows the status of all inserted and deleted comments in your document.

-   **A**: Select a review task to see review comments. If your topic has been shared for review in multiple review tasks, you will see those tasks listed in this drop-down.

    When you select a review task from the list, you get to see the comments made by reviewers in that task. You can address the review comments independently in tasks, which mean that any update on a comment is visible to reviewers of that respective task only.

-   **B:** The **Review details** are listed. Each **Review Project** is created on a specific version of the document. The **Review Version** displays the version associated with the selected review project. This helps you to keep a track of the version that you had shared for review.
    Select **Review details** ![](images/active-review-info-icon.svg)in the **Comments** panel to view more information about the review task:

    - Name of the project
    - Review version
    - Status
    
    >[!NOTE]
    >
    > If the root map of your review task is different from the authoring root map, it displays the
    information about it to indicate that the authoring and the review root map don’t match.

-   **C**: If you have updated your topic after initiating the review, then clicking on Revert Topic to Review Version icon reverts your working copy back to the version that was shared for review. This makes it easier for you to incorporate the review feedback directly in the version that was shared for review. After incorporating the feedback, you can save changes in the reverted version or create a new revision of your topic. If you choose to create a new revision of your topic, then a new branch is created from the topic version that was shared for review. For example, if you shared version `1.2` of a topic for review while the current authoring version is `1.3`, then you can use this icon to switch back to version `1.2` for incorporating review comments. If you choose to create a new revision after incorporating changes to version `1.2`, then a new branch with version `1.2.0` is created for the topic.

    Typically, after incorporating review feedback, you would like to merge changes from the latest version of the topic. To do so, use the [Merge](web-editor-features.md#id205DF04E0HS) feature to get all updates made after the topic was shared for review.

-   **D**: Open the side-by-side view to display the commented version of the topic. As seen in the above screenshot, the leftmost section is the latest version of the topic wherein you can make changes. The next section is the commented version of the topic. As you navigate between comments in the topic, the side view changes and displays that version of the topic on which the comment was made. Each comment in the comment panel is linked to the corresponding text in this section. It helps you identify the commented text. The comments are displayed in the order of the commented text in the document.

    You can see the version number at the top of the side view. Clicking on this icon again hides the commented version of the topic.

-   E: Import the inserted and deleted \(or Strikethrough\) comments in the topic directly. After clicking the Import icon, all text insertions and deletions are shown in the working copy of the topic. Now, there are two ways of accepting or rejecting comments.

    If you want to incorporate the suggested change \(insertion or deletion\) one at a time, simply right-click on the comment in the content and select Accept Change or Reject Change. Depending on your selection, the comment is accepted or rejected. In case of accepted comment, the content is added in the content; and in case of rejection, it is removed from the content. Also, the status of the comment is changed in the Review panel.

    ![](images/import-comment-accept-web-editor_cs.png){width="800" align="left"}

    You can also use the review feature in the right panel to accept or reject comments. Clicking on any comment highlights the comment in the document.

    ![](images/changes-tab_cs.png){width="800" align="left"}

    >[!IMPORTANT]
    >
    > The import comments feature works only on those documents that have not changed since they were shared for review. If you have made any change after sending the document for review, you will get an alert to **Force Import** comments into your document. However, doing so will result in loss of all updates that you have made in your document. The **Force Import** alert is also shown if the document is created outside and then shared for review. You can go ahead and import the comments.

    As and when you accept or reject a comment, it is removed from the Tracked Changes list. This also serves as an indicator of how many comments need to be addressed in the document.

-   **F**: From the More Options menu, Download all attachments available in the review topic.
-   **G**: Search for a text within comments.
-   **H**: Accept or reject a comment.

-   **I**: Apply a filter on the comments. You can filter to see comments on the basis of Review Type \(all, highlighted, deleted, inserted, or sticky note\), Review Status \(all, accepted, rejected, or none\), Reviewers \(all or specific reviewer\(s\)\), or Versions of topic.


**Parent topic:**[Review topics or maps](review.md)
