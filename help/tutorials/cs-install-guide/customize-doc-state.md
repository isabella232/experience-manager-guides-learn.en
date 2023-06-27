---
title: Configure document states
description: Learn how to Configure document states
---

# Configure document states {#id181GB0400UI}

AEM Guides lets you define the document states for your DITA topics according to your organization's requirements. You can define different states of your document from start to the end. For example, the first state can be Draft and it can move to Review, Approved, Translated, and finally to Published.

There are two ways in which a topic can transition from one state to another - manual and automatic. The document states that are defined in a profile can be used for manually changing the document state. This can be done from the Properties page of a topic file. Also, you can define who can move the document from one state to another state. For example, an author can create a document and the default state of the document can be Draft. When the author sends the document for review she can change the document state to In-Review. The reviewer can change the document state to either Approved or to Draft again based on the review process. If the document is Approved, the publisher can change the document state to Translated or Published depending on the workflow.

>[!NOTE]
>
> If a user belongs to the *administrators* group, the user can change a document's state from any state irrespective of the document state transitions defined in the system.

## Create a document state 

AEM Guides is shipped with a set of default document states. These states are:

-   Draft
-   Edit
-   In-Review
-   Approved
-   Reviewed
-   Done

These default states are available to all DITA topics created under DAM. You can create your own document states and assign these to a specific folder. All DITA files created under that folder will then have access to the newly created document states.

To create document states using the Folder Profile, perform the following steps:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides**from the list of tools.
1.  Click on the Document States tile.

    Assets States page is displayed. By default, the page shows a default profile.

1.  Click **Create Profile** and enter the following details:
    -   Enter the name for the profile in the Profile field.
    -   Specify the path where you want to apply the new profile.
    -   Specify the states of the document in the **Allowed States** under **States**. The default document states are Draft, Edit, In-Review, Approved, and Done.-

        Click the **Add** button to add a document state.

        - Click the Delete icon to delete a document state.

        >[!NOTE]
        >
        > Do not delete a document state if documents are still in that state. If you delete a document state, you won't be able to change the document state of such documents unless you belong to the *administrator* user group.

    -   Specify the start state of the document in the **Start State**.
    -   Specify the end state of the document in the **End State**.
    -   Specify the state transition of the document in **From** and **To** under **State Transition**.

        - Specify the users and user groups who can change the document state in **Groups**.

        - Click the **Add** button to add a state transition.

        - Click the Delete icon to delete a state transition.

        >[!NOTE]
        >
        > Do not delete a state transition if documents are still in `From` state. If you delete a state transition, you won't be able to change the document state of such documents unless you belong to the *administrator* user group.

1.  Click **Done**.

## Create a copy of a document state profile 

Depending on your requirement, you can create a copy of an existing document state profile. You can use the copy as a base for creating another document profile.

To create a copy of a document state profile, perform the following steps:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides**from the list of tools.
1.  Click on the Document States tile.

    Assets States page is displayed.

1.  Select the document state profile that you want to duplicate and click **Duplicate Profile**.
1.  Make required changes and click **Done**.

## Delete a document state or state transition 

>[!NOTE]
>
> Do not delete a document state or state transition if documents are still in the state or in state transition. If you delete a state or state transition, you won't be able to change the document state of such documents unless you belong to the *administrator* user group.

Perform the following steps to delete a document state or state transition from a document state profile:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools.
1.  Click on the Document States tile.

    Assets States page is displayed.

1.  Select the document state profile from where you want to delete the document state and click **Edit Profile**.
1.  Delete the document state or state transition and click **Done**.

## Delete a document state profile 

To delete a document state profile, perform the following steps:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select**Guides** from the list of tools.
1.  Click on the **Document States** tile.

    Assets States page is displayed.

1.  Select the document state profile that you want to delete and click **Delete Profile**.

## Automate the document state change 

If you do not want to manually change the document states, you can create a workflow and automate the document state change.

>[!NOTE]
>
> Automated workflows should be in conformance with the document states and transitions defined in the configuration. The system does not perform any checks for state changes done through automated workflows.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Workflow** from the list of tools.

1.  Click on the **Models** tile.

1.  Select the relevant workflow, say Review Topics.

1.  Click **Edit**.

    The workflow opens up in a new tab.

1.  Click **Edit** \(top-right\).

1.  Open the **Steps** browser; using **Toggle Side Panel**, at the far left of the top toolbar

1.  Drag the appropriate step\(s\) to the required location in the model.

1.  Click the new step you added in the workflow model and select **Configure** from the component toolbar

1. Open the **Process** tab.

1. In the **Process** drop-down list, select **Set Document State for Any DAM Asset**.

1. Select the **Handler Advance** option.

    ![](assets/update-workflow-doc-state_cs.png)

1. In the **Arguments** text box, enter a document state to which you want to transition from the selected workflow.

    >[!NOTE]
    >
    > Ensure that you enter the correct document state in the Arguments text box. If you enter an incorrect value, then the document will be set to an incorrect state.

1. Confirm the change with **Save & Close**.


## Enable approval workflow 

AEM Guides provides document approval workflow, which helps you to control the lifecycle of your document development process. To enable the approval workflow, perform the following steps:

1.  To download the UI configuration file log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click**Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system. You can then make changes to the file and then upload the same.
1.  In the `ui_config.json` file, enable the approval workflow feature by changing the *features* section as shown below:

    ```
    "features":  
    { 
       "approvalWorkflow":  true 
    }
    ```

1.  Save the file and upload it.

