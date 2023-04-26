---
title: Document state
description: Learn how to Document state
exl-id: 6ab85a63-02d2-4802-a6b8-99e6551a567b
---
# Document state {#id1821HC00URO}

To manage the readiness of the documents, AEM Guides provides document state property to indicate the current state of the document. Document states help you quickly find out whether a document is new, in review, or review completed state.

## Types of document states 

A document can have any of the document states defined in the Document State profile. For example, a document may have any one of the following Document States:

-   Draft - Indicates that the document is created and saved with new changes.
-   In-Review - Indicates that a review workflow has been initiated for the document.
-   Reviewed - Indicates that the document has been reviewed by the intended users.

These states are set manually or automatically according to the Document States profile settings. For example, if the Document State profile is configured with start state as Draft, and In-Review state is defined for documents under review. Then, when you create a document, the document state is set to *Draft*. If you initiate a review task, then the state of the document is changed to In-Review.

You can also manually change the document state for a single or multiple documents. However, if you choose to change the document state for multiple documents, then the allowed state is determined by the common states that are allowed for the selected documents. For example, let's say you have defined the document states as Draft, In-Review, Reviewed, and Ready to Publish, in the same order. On document one.dita the state is set to *Draft* and on document two.dita, the state is set to Reviewed. When you select both—one.dita and two.dita, then the allowed document state will be *Ready to Publish*. As two.dita is in *Reviewed* state, the next possible state for two.dita is only *Ready to Publish*, which is shown when both documents are selected.

>[!NOTE]
>
> A document can exist in only one state at a time.

## Change document state 

To change the state of a document, perform the following steps:

1.  In the Assets UI, select one ore more document for which you want to change the document state.
1.  In the main toolbar, click **Properties**.
1.  Select the new state from the **Document State** drop-down. You can select only those document states that are allowed in the State Transition section of the Document State profile.

    >[!NOTE]
    >
    >Administrators can see all document states and change the document to any possible state.

1.  Click **Save & Close**.

## View document state 

The card view of the Assets UI shows the current state along with the creation date and size of the respective DITA topic or DITA map.

![](images/document_state.png){width="800" align="left"}

## Use document states in DDLC 

Document states play an important role in managing the lifecycle of documents in DDLC. If your organization strictly follows the DDLC, then having a mechanism to control editing documents based on their state becomes an essential feature. For example, you can allow editing documents when they are in *Draft* or *In-review* states. However, once a document is reviewed and is ready to publish, then there should be a way to prevent further modification of documents.

AEM Guides provides document approval workflow, which helps you to control the lifecycle of your document development process. Once a document is ready to publish or has reached the penultimate state, you can mark it as approved. Once a document is approved, AEM Guides creates a new version of the document and makes it read-only. You can then move the document for publishing or create a baseline for further processing.

To start a new release form the documents that are marked as approved, an author has to start a new release. Starting a new release changes the document state to *Draft* again. By changing the document state to *Draft*, the document is again made editable and you can continue working on the next release.

To use the document approval feature, perform the following steps:

>[!NOTE]
>
> The approval workflow feature must be enabled by your administrator. For more details, see *Enable approval workflow* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

1.  In the Web Editor, open the document that you to mark for approval.

1.  Click the **Mark Approved**![](images/mark_approve_icon.svg)icon.

1.  If your document is in the state to be marked as approved, the following dialog appears:

    ![](images/mark-approved-correct-state.png){width="550" align="left"}

    If your document cannot be marked as approved, then the following message is displayed:

    ![](images/mark-approved-incorrect-state.png){width="550" align="left"}

1.  If your document is ready to be marked as approved, then select a label from the drop-down list and click **Approve**.

    >[!NOTE]
    >
    > If your administrator has not configured a predefined list of labels, then you are shown a free-form text field to enter a label.

1.  Once the document is successfully marked as approved, then a **Preview** of the document is shown in the read-only mode.

    ![](images/approved-doc-read-only.png){width="650" align="left"}

    >[!NOTE]
    >
    > In the Preview mode all editing options are removed from the toolbar. In addition, the Author and Source view of the document as also removed from the top navigation.


Once a document is marked as approved, it is no longer available for editing. If you want to use the document for the next release, then you need to bring it back to the *Draft* state. To change the document state of an approved document back to *Draft* mode, perform the following steps:

1.  In an approved document, click the **Start a New Release** Icon ![](images/approved-restart-draft-mode-icon.svg).

    The Start New Release message appears.

1.  Click **Confirm**.

    The document's state is changed to Draft and the document is opened in the Web Editor in the edit mode.


**Parent topic:**[Work with the Web Editor](web-editor.md)
