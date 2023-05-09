# Configure document states {#id181GB0400UI}

AEM Guides lets you define the document states for your DITA topics according to your organization's requirements. You can define different states of your document from start to the end. For example, the first state can be Draft and it can move to Review, Approved, Translated, and finally to Published.

There are two ways in which a topic can transition from one state to another—manual and automatic. The document states that are defined in a profile can be used for manually changing the document state. This can be done from the Properties page of a topic file. Also, you can define who can move the document from one state to another state. For example, an author can create a document and the default state of the document can be Draft. When the author sends the document for review she can change the document state to In-Review. The reviewer can change the document state to either Approved or to Draft again based on the review process. If the document is Approved, the publisher can change the document state to Translated or Published depending on the workflow.

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
1.  Select **Guides** from the list of tools.
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
1.  Select **Guides** from the list of tools.
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
1.  Select **Guides** from the list of tools.
1.  Click on the Document States tile.

    Assets States page is displayed.

1.  Select the document state profile that you want to delete and click **Delete Profile**.

## Automate the document state change 

If you do not want to manually change the document states, you can create a workflow and automate the document state change.

>[!NOTE]
>
> Automated workflows should be in conformance with the document states and transitions defined in the configuration. The system does not perform any checks for state changes done through automated workflows.

Perform the following steps to automate the document state change:

1.  Open the workflow page from the AEM server URL.

    `<AEM_Server_URL>:<port>/workflow`

1.  Open a workflow from the workflow page. For example, Review Topic.
1.  Select **Process Step** from the **Workflow** section of the AEM dialog and drag-drop on the workflow.

    ![](assets/process-step-workflow.png)

1.  Double-click the process and open the **Step Properties** dialog.
1.  Enter the following details in the **Process** tab of the dialog and click OK:
    -   Select **Set Document State for any DAM asset** from the Process drop-down.
    -   Select the Handler Advance check-box.
    -   Enter the name of the document state in the **Arguments** text box.

        >[!NOTE]
        >
        > Make sure that you enter the correct document state in the Argument text box. If you enter a wrong name, the document will be set to the wrong document state.

1.  Click **Save** to save the workflow.

## Enable approval workflow 

AEM Guides provides document approval workflow, which helps you to control the lifecycle of your document development process. To enable the approval workflow, perform the following steps:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the default configuration file available at the following location:

    `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1.  Create a copy of the default configuration file at the following location:

    `/apps/fmdita/xmleditor/ui_config.json`

1.  Navigate to and open the `ui_config.json` file in the `apps` node for editing.

1.  In the `ui_config.json` file, enable the approval workflow feature by changing the *features* section as shown below:

    ```json
    "features":  
    { 
       "approvalWorkflow":  true 
    }
    ```


