---
title: Review topics
description: Learn how to Review topics
---

# Review topics {#id2056B0W0FBI}

If you are a reviewer, then you receive a review request email with the link to the review topics. Clicking on the link takes you to the review page wherein you can add your feedback on the shared topics.

Perform the following steps to review a topic:

1.  Click the direct link given in the review request email.

    The topic or map link is opened in a browser.

    >[!NOTE]
    >
    > You can also access the topic review link from your Inbox notifications area in the AEM user interface.

1.  Depending on the way the topic review is initiated, you could see any one of the following two screens:

    >[!NOTE]
    >
    > The UI may be different if you have created the review in:
    >
    > - AEM Guides as a Cloud Service November 2022 release or earlier
    > - AEM Guides version 4.1 or earlier



    The following screen appears when a DITA map is used to initiate the review workflow:

    ![](images/multiple-topics-review.png)

    The following options are available on this screen:

    -   **A**: The name of the review task.
    -   **B**: Click the Topics View icon to show or hide the topics panel.

    -   **C**: The numbers highlighted by ***F*** can be filtered by choosing the desired filter option from here. You can filter comments by its type, status, reviewer, or version. For example, if you want to see how many Strikethrough comments have been made in each of the under review topic, click the filter icon and then choose **Review Type** \> **Deletion**.

        >[!NOTE]
        >
        > On applying the fiters, only the comments which match the selected filters are displayed in the comments panel. The number of filtered comments are shown on the left in the topics panel.

    -   **D**: A topic that is assigned for review to the current reviewer is shown in black and is clickable. When the reviewer clicks on a topic link that topic is brought to the top of the screen.
    -   **E**: A topic that is not available for review is grayed out. The topic is shown in read-only mode and you are not allowed to add any review comments on such topics.

    -   **F**: Number of comments received on a topic. This number changes based on the filter that you apply.

    All topics in the map are shown as a single composite document. The topics that the reviewer is allowed to review are shown normally. The topics that the review is not allowed to review are not shown.

    ![](images/review-read-only.png)

    In the above screenshot, the General description topic is shared for review the current reviewer,which is shown normally. However, the next topic, History of flight content is not shared for review and it is shown in read-only mode. The topic which is currently in focus is also highlighted in the TOC.

    The following screen appears when a topic or multiple topics are selected and shared for review:

    ![](images/review-composite-view.png)

    >[!NOTE]
    >
    > In case of multiple topics, they are shown as one composite document in the document view. The above screenshot highlights two different topics presented one after the other in a single view.

1.  Open the Comments panel by clicking the **Comments** icon at the top-right corner of the toolbar.

    Provide review comments by selecting an appropriate comment type from the toolbar and press Enter to submit your comment.

    >[!NOTE]
    >
    > The Comments panel shows the comments given on the current topics only. When you move focus to other topic, the comments given on the other topic are shown.

1.  Click **Close** button once you complete reviewing the topic. On clicking the **Close** button, you will be redirected to the page from where you accessed the review topic.

## Addition features available on the review screen 

**Document view and topic view** - By default, if multiple topics are shared for review, then a composite document view of topics is shown to the reviewers. In case of a DITA map review, all topics in the map are presented in the form of a single document, resembling a book view. If you want, you can also click on a particular topic and only that topic is then shown on the review screen.

When you view a single topic, then you get an additional option to switch back to the document view. In the following screenshot, a particular topic from a map file is opened for review. The highlighted option — **Show Document View** allows user to switch back to the document view of the map file.

![](images/switch-document-view.png)

**Working with different types of commenting tools** - You can add inline comments by highlighting text, striking through text, inserting text, or adding a comment note. The different types of commenting tools provided in the Comments toolbar are described below:

![](images/comments-toolbar.png)

-   **Highlight** \(![](images/review-highlight-icon.svg)\): To add a highlight comment, select the text and click the Highlight icon. Or, click the Highlight icon and select the desired text:

    ![](images/highlight-comment.png)

    A pop-up appears in the Comments panel wherein you can add your comment for the highlighted content.

-   **Strikethrough** \(![](images/review-text-strike-through-icon.svg)\): If you want to suggest content removal, you can do so by selecting the content and clicking the Strikethrough icon. Or, select the desired text and click the Delete key:

    A pop-up appears in the Comments panel wherein you can add your comment for the deleted content.

-   **Insert Text** \(![](images/review-insert-text-icon.svg)\): If you want to insert text, click the Insert Text icon and place the cursor where you want to insert the text and type in the information. Or, place the cursor where you want to insert text and start typing. The added information appears in green colored font:

-   **Add Comment**\(![](images/review-comment-icon.svg)\): If you want to add a sticky note type of comment, click the Add Comment icon and enter the comment in the pop-up.


**Contextual toolbar**

You can also highlight or strikethrough text quickly with the contextual toolbar. Perform the following steps to comment using the contextual toolbar:

1.  Select the text you want to highlight or strike through. The contextual toolbar appears.

    ![](images/review-quick-launch-toolbar.png)

1.  Click the **Highlight**or **Strikethrough** icon.
1.  You can add comments in the comment panel for the highlight or strikethrough action.

**Review using the Comments panel** - The Comments panel displays a list of comments given on the current topic. This panel also lists comments from other reviewers, if the topic is sent to multiple reviewers. Each comment in the comment panel is linked to the corresponding text in the current topic. It helps you identify the commented text. Each comment displays the name of the reviewer who has added the comment along with the timestamp.

The comments are displayed in the order of the commented text in the document. For example, there is a highlight comment on the first sentence and an insert text comment on the second sentence in the first paragraph then the highlight text comment is displayed before the inserted text comment.

The tasks that you can perform using the Comments panel are described below:

-   Clicking on a comment highlights and shows the corresponding comment's location in the document.
-   You can add replies to comments.
-   You can edit your own comment by clicking on your commented text in the Comments panel and then selecting **Edit** from the Options menu.
-   You can delete your own comments by clicking on the comment in the Comments panel and then selecting the **Delete** option from the Options menu.

    ![](images/review-comment-options-menu.png)

    >[!NOTE]
    >
    > The Options menu appears only when you hover over your own comments. It is not displayed for the comments by other reviewers.

-   All participating users can respond to comments submitted by other users. On a comment, click **Reply** and press Enter to submit a response.

**Preview mode**

- Opening a topic in the Preview mode shows how a topic will be displayed when it is viewed by an author after applying all the changes. For example, all inserted text is shown as normal text and all striked off \(deleted\) text is removed from the content.

- The following screenshot shows the content in *Review* mode:

![](images/review-author-mode.png)

The following screenshot shows the content in *Preview* mode:

![](images/review-preview-mode.png)

**Add attachments to comments** -   If you want to supplement your comment by providing additional information which is available in some other file, you can do so by attaching it with your comment. As a reviewer, you can easily add one or multiple files from your local system to your comment. A file can be added to all supported forms of comments - Highlight, Strikethrough, Insert Text, or a Comment.

When you insert any of the comments, the commenting pop-up appears. After providing additional comments or information in the pop-up, you submit it by hitting Enter. Once the comment is added, you get the option to add an attachment to that comment.

![](images/comment-pop-up-panel.png)

In the above screenshot, the document contains the highlight comment's pop-up and the comment is also added in the Comments panel. The file attachment icon ![](images/file-attach-review.svg)is available along with the comment at both the locations.

Perform the following steps to add attachment to your comment:

1.  Click the *Add Attachment* icon ![](images/file-attach-review.svg) on the comment with which you want to add an attachment.

    The file Open dialog appears.

1.  Select one or multiple files you want to attach.

    The selected files are shown along with the comment in the Comments panel.

    In the Comments panel you can see the file name and its size. You also have an option to remove a file by clicking the delete icon ![](images/Delete_icon.svg) associated with the file name.

1.  Click **Submit**.

    The attachments are uploaded and added to the comment.


**Additional notes on working with attachments:**

-   By default, only two files attached with a comment are shown. If there are more files, then **View Attachment** button on the right shows the number of all attachments \(which are more than two\) associated with the comment. You can click the number to view all attachments. For example, if you have four attachments with a comment, you will see +2 on the button.

![](images/review-view-attachment.png)

-   Hovering the mouse pointer over an attachment gives the options to download or remove the attachment. Removing the attachment is available only if the current reviewer has added that comment, as shown the following screenshot:

![](images/current-user-comment-options.png)

The other reviewers or authors get only the download attachment option.

![](images/other-reviewer-download.png)

-   You can download all attachments associated with a comment from the **View Attachments** dialog. Select the attachments and click the **Download** icon at the comment level.

-   You can also delete the attachments associated with a comment from the **View Attachments** dialog. Select the attachments and click the **Delete** icon.

![](images/attach-files-comments-panel.png)


**Conditions panel** -   If your topic has conditional content, then you will see the **Conditions** \(![](images/conditions-icon.svg)\) icon on the right. Clicking on **Conditions** icon opens the Conditions panel that allows you to highlight the content as per the available conditions in the topic.

:   By default **Highlight All Conditions** option is enabled, all conditions are selected, the entire content is displayed, and the conditionalized content is shown as highlighted both in review and preview mode.

:   You can disable **Highlight All Conditions** option and see all the content present in the topic as normal text without any highlights.

![](images/review-conditions-panel.png)

You can choose to hide or show a specific condition.

-   If you hide a condition, the content having that condition is not highlighted in the review mode.
-   If you show a condition conditionalized content is highlighted in the review mode. For example, in the following screenshot, only the content uses two conditions - `win` and `mac` is highlighted.


![](images/review-condition-normal-mode.png)

In the preview mode, the non-conditionalized content and the conditionalized content that uses the two shown conditions - `win` and `mac` is displayed. The remaining conditionalized content for which the conditions are hidden is not displayed.

**Real-time review** -   The Comments panel updates in real time with comments and the feedback or action taken by the author on the comments.

-   Multiple reviewers will be able to leave comments or reply to comments simultaneously on the same document. You can find out who is currently reviewing the document by hovering the mouse over the user icon at the top-right corner of the screen.

-   If a topic is a part of multiple review tasks, then the comments made in one task are not shown in the other task.

-   Clicking Outdated Comment icon \(![](images/outdated-comment-icon.svg)\) displays the differences in between the latest and the commented version of the document. The version numbers \(of the versions that are being compared\) are displayed at the top of the documents.

    ![](images/comments-page-review-mode.png)

    >[!NOTE]
    >
    > When you hover over the Outdated Comment icon, the version number of the topic on which the comment was added, is displayed. For example, if a comment was given on version 1.0, the same is displayed.

-   Clicking an outdated comment opens the version of that comment in the left panel. The previous version is shown in the left panel and the current version is displayed in the right panel. All comments on the outdated version are imported on the left side. You can compare the previous version with the current version.

**Filter comments** -   You can filter comments in a document to view specific comments as required. To filter comments, click the **Filter** icon \(![](images/filter-search-icon.svg)\) that appears in the menu on the right of the Search Comments text box in the Comments panel.

Select one or more of the following filtering options from the **Filter Type** dialog and click **Apply**.

-   **Review Type** - Filter on the basis of the comments type – Highlight, Deletion, Insertion, or Comment.
-   **Review Status** - Filter on the basis of the status of the comment like Accepted, Rejected, or None.
-   **Reviewers** - Filter on the basis of the reviewer's name.

-   **Versions** - Filter on the basis of the comments received on a particular version of the topic.

    On using the filters the comments on the right panel get filtered according to the selection, and the number of comments in the left panel is updated accordingly.


To remove the filter and view all the comments, deselelect all filters from the **Filter Type** dialog and click **Apply**.

**Parent topic:**[Review topics or maps](review.md)

