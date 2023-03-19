# Generate output for a DITA map from the map console {#id1825FG00UHT}

Perform the following steps to generate output for a DITA map:

1.  In the Assets UI, navigate to and click on the DITA map file that you want to publish.

    The DITA map console appears with the list of Output Presets available to generate output.

1.  Select one or multiple Output Presets that you want to use for generating the output.

    ![](images/generate-multiple-outputs-uuid.png)

    >[!NOTE]
    >
    > If you are generating the AEM Site output, then the publishing process uses the structure defined in the `.ditamap` file to create AEM Site structure.

1.  Click the Generate icon to start the output generation process.


You can view the current status of the output generation request by clicking on Outputs. For more information, see [View the status of the output generation task](#viewing_output_history)

>[!IMPORTANT]
>
> If an output generation process for a preset is either in the queue or in progress, you cannot initiate another output generation task for the same preset.

You can generate the PDF output for one or more output presets created for a DITA map from the Web Editor. For more details, see [Use Quick Generate panel to generate and view output for the presets](web-editor-quick-generate-panel.md#).

You can also generate the AEM Site output for one or more topics, or the entire DITA map from the Web Editor. For more details, see [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

## Incremental output generation {#generating_standalone_topic}

>[!NOTE]
>
> Incremental output generation is applicable only for AEM Site output. Also, you can only regenerate DITA \(.dita/.xml\) topics from a DITA map or sub-maps. If you select a DITA map, sub-map, topic group, or a topic with `@processing-role="resource-only"`, then the regenerate option is not available.

There could be a number of instances where you would update only a few topics in your DITA map and push only those updated topics live. To handle such scenarios, AEM Guides allows you to create incremental outputs. If you have updated a few topics, you do not need to regenerate the entire DITA map. You can select only the updated topics and regenerate them.

If your map is chunked and you have updated a single topic in that map, then you need to regenerate the entire map for the updated topic or content to reflect in the output. You will not get the output regeneration option at a topic level, it is only available at the \(chunked\) map level. This is applicable to the parent map and all sub-maps.

Perform the following steps to regenerate output for a specific topic or a group of topics:

>[!IMPORTANT]
>
> When you are regenerating the AEM Site output, then the output is created using the current version of the files and not the attached Baseline.

1.  In the Assets UI, navigate to and click on the DITA map file.

    The DITA map console appears with the list of Output Presets available to generate output.

1.  Select the **Topics** tab.

    A list of topics available in the DITA map is displayed.

1.  Select the topics that you want to regenerate.

    >[!NOTE]
    >
    > If you have added new topics to the DITA map, you will not be able to generate those new topics from here. You must first publish the newly added topics by using the DITA map publish function.

    ![](images/regenerate-topics.png)

1.  Click **Regenerate**.

    The Regenerate Selected Topics page appears.

1.  Select the output preset that you want to use to regenerate the selected topics.

1.  Click **Regenerate** to start the output generation process.


>[!IMPORTANT]
>
> If you rename a topic title and regenerate the topic, the updated topic title does not reflect in the DITA map table of contents. To update the topic title in the TOC, you must generate the entire DITA map.

You can view the current status of the output generation request by clicking on Outputs. For more information, see [View the status of the output generation task](#viewing_output_history).

## View the status of the output generation task {#viewing_output_history}

Once you initiate the output generation task for a map or regenerate selected topics, AEM Guides sends this task to the output generation queue. This queue is updated in real time, showing the status of each output generation task in the queue.

Perform the following steps to view the output generation queue:

1.  In the Assets UI, navigate to and click on the map file for which you want to check the output generation status.

1.  Click **Outputs**.

    ![](images/output-queued.png)

    The Outputs page is divided into two parts:

    -   **Queued Outputs:**

        Lists the outputs that are either waiting to be generated or are under generation process. The queued or in progress tasks are shown with a blue color icon before the preset name. You can also find the output generation setting or preset used for the queued task, the type, user who initiated the task, time since when the task is queued, and the current status.

        Click on the link to access the **Publish Dashboard** and view the current running status. A list of all active publishing tasks is available in the Publish Dashboard. The **Queued Outputs** and the **Publish Dashboard**link are displayed only when there are outputs that are either waiting to be generated or are under generation process. They don't appear when the output tasks have been completed.For more details on Publish Dashboard, see [Manage publish tasks using the Publish Dashboard](generate-output-publish-dashboard.md#).

    -   **Generated Outputs**

        Lists the output tasks that have been completed. Again, the information shown here is similar to the Queued Outputs section with a few differences. You have new set of information in the form of output result icon and the output generation time.

        In this list, you could have tasks that have executed successfully, tasks that have executed with message, or failed tasks. The successful tasks are shown with green color icon, the tasks with a message have an orange color icon, and the failed tasks are shown with red color icon.

        For all the tasks, the publishing process creates a log file \(logs.txt\) that can be accessed by clicking the link in the Generated At column. For tasks that have failed or have messages, you can check the log file, which is explained in the section [View and check the log file](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

        >[!NOTE]
        >
        > When you click on a link of the generated PDF output, you are asked to download the PDF. This is the default behavior in AEM 6.5 and 6.4.


## Cancel an output generation task {#id2061H100T5Z}

AEM Guides gives publishers a simple and easy way to cancel any ongoing publishing task. As a publisher, you can cancel an ongoing publishing task from the DITA map console or the [Publish Dashboard](generate-output-publish-dashboard.md#).

Perform the following steps to cancel an output generation task from the DITA map console:

1.  In the Assets UI, navigate to and click on the map file for which you want to cancel an ongoing output generation task.

1.  Click **Outputs**.

1.  In the Queued Outputs list, hover the pointer over a task that you want to cancel.

1.  Click the *Cancel This Job* icon.

    ![](images/cancel-publish-task-map-console.png)

1.  Click **Yes** on the Confirm Cancellation message prompt.

    ![](images/confirm-cancel-output-map-condole.png)

    If the task has not yet started, the cancel command is executed on the task. For a task that is being canceled, the Status is set to Canceling.

    Once the task is successfully canceled, it is moved to the **Generated Outputs** list with a **Cancelled** status. When you hover over the canceled task, it shows the name of the user who has canceled the task. In the following screenshot, the *HTML5* task is canceled.

    ![](images/cancelled-output-task.png)


## Delete an output task from DITA map console 

When you generate multiple outputs for a DITA map, over a period of time the Generated Outputs list for such a map becomes very long. As a publisher you can clean the output history of any map file by removing the outdated tasks from the *Generated Outputs* list. Note that the output is not removed from the system, only the entry of the generated output is removed from the *Generated Outputs* list.

Perform the following steps to remove an output task from the Generated Output list:

1.  In the Assets UI, navigate to and click on the map file from which you want to delete the tasks.

1.  Click **Outputs**.

1.  In the Generated Outputs list, hover the pointer over a task that you want to delete.

1.  Click the delete icon.

    ![](images/delete-output-task.png)

1.  Click **Yes** on the Confirm Delete message prompt.

    The task is deleted from the Generated Outputs list.


**Parent topic:**[Output generation](generate-output.md)

