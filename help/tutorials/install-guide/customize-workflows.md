# Configure and customize workflows {#id181AI0OJ0RO}

Workflows enable you to automate Adobe Experience Manager \(AEM\) activities. A workflow consists of a series of steps that are executed in a specific order. You can define a distinct activity to execute on each step. For example, you can send an email notification to all reviewers in a group when a topic review is created. Or, send a notification to the publisher when an output generation task completes.

For more information about workflows in AEM, see:

-   [Administering Workflows](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html)

-   Applying and participating in workflows: [Working with Workflows](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/workflows.html).

-   Creating workflow models and extending workflow functionality: [Developing and Extending Workflows](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/workflows.html).

-   Improving the performance of workflows that use significant server resources: [Concurrent Workflow Processing](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


The sections in this topic will walk you through various customizations that you can make in the default workflows shipped in AEM Guides.

## Customize review workflow {#id176NE0C00HS}

Every organization's content authoring team works in a specific way to meet their business requirements. In some organizations there is a dedicated editor, whereas some other organization could have automated editorial review system in place. For example, in an organization a typical authoring and publishing workflow could include tasks like - whenever an author is done with authoring content, it automatically goes to the reviewers, and when the review is complete it goes to the publisher for generating the final output. In AEM, activities that you do on your content and assets can be combined in the form of a process and mapped to an AEM workflow. For more information about workflows in AEM, see [Administering Workflows](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html) in AEM documentation.

AEM Guides allows you to customize the default review workflow. You can use the following four custom review-related processes with your other authoring or publishing workflows.

-   **Create Review**: This process prepares the metadata required to create a review task. For example, it will assign review permission to the reviewers, set the status of the topics to under review, set the review timelines, and more. Out of the four processes, this is the only mandatory process that must be included in your custom workflow. In your workflow, you may choose to include or exclude the other three processes.

-   **Assign Review Task**: This process creates the review task and sends the task notification to the initiator and reviewers.

-   **Send Review Email**: This process sends the review email to the initiator and reviewers.

-   **Schedule Job to Close Review**: This process ensures that the review process completes on reaching the deadline.


When you are creating a custom review workflow, the first task is to set the required metadata needed by the Create Review process. To do so, you can create an ECMA script. A sample of the ECMA script that assigns the metadata is given below:

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
```

You can create this script in the `/etc/workflows/scripts` node. The following table describes the properties being assigned by this ECMA script:

|Property|Type|Description|
|--------|----|-----------|
|`initiator`|String|User ID of the user initiating the review task.|
|`operation`|String|A static value set as `AEM_REVIEW`.|
|`orgTopics`|String|Path of the topics being shared for review. Specify multiple topics separated by comma.|
|`payloadJson`|JSON object|Specify the following values: -   `base`: path of the parent folder containing the topic sent for review.

-   `asset`: path of the topic sent for review.
-   `referrer`: leave it blank.

|
|`deadline`|String|Specify the time in `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` format.|
|`title`|String|Enter a title for the review task.|
|`description`|String|Enter a description for the review task.|
|`assignee`|String|User ID of the users to whom you want to send the topic\(s\) for review.|
|`status`|Integer|A static value set as 1.|
|`startTime`|Long|Use the `System.currentTimeMillis()` function to get the current system time.|

Once you have created the script, call it before calling the Create Review process in your workflow. Then, depending on your requirements, you can call the other review workflow processes.

### Remove review workflow from the purge configuration 

To improve the workflow engine performance, you can regularly purge completed workflow instances from the AEM repository. If you are using the default AEM configurations, then all completed workflow instances are cleaned up after a specific period of time. This also results in all review workflows to get purged from the AEM repository.

You can prevent review workflows from auto-purging by removing the review workflow model \(information\) from the auto-purge configuration. You need to use the **Adobe Granite Workflow Purge Configuration** to remove the review workflow models from auto-purging list.

In the **Adobe Granite Workflow Purge Configuration**, ensure that you list at least one workflow that you can safely purge. For example, you can use any of the following workflows created by AEM Guides:

-   /etc/workflow/models/publishditamap/jcr:content/model
-   /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Adding a workflow in the **Adobe Granite Workflow Purge Configuration** ensures that AEM purges only those workflows that are listed in the configuration. This prevents AEM from purging the review workflow information.

For more details about configuring the **Adobe Granite Workflow Purge Configuration**, see *Administering Workflow Instances* in AEM documentation.

### Customize email templates 

A number of the AEM Guides workflows make use of email notifications. For example, if you initiate a review task, an email notification is sent to the reviewers. However, to ensure that the email notification is sent, you have to enable this functionality in AEM. To enable email notification in AEM, see the article [Configuring Email Notification](https://docs.adobe.com/docs/en/aem/6-1/administer/operations/notification.html) in AEM documentation.

AEM Guides contains a set of email templates that you can customize. Perform the following steps to customize these templates:

1.  Log into AEM and open the CRXDE Lite mode.

1.  In the Navigator tab, go to the following location:

    `/libs/fmdita/mail`

    >[!NOTE]
    >
    > Do not make any customizations in the default configuration files available in the ``libs`` node. You must create an overlay of the ``libs`` node in the ``apps`` node and update the required files in the ``apps`` node only.

1.  The mail folder contains the following customizable templates:

    |Template Filename|Description|
    |-----------------|-----------|
    |closereview.html|This email template is used when a review task is closed.|
    |createreview.html|This email template is used when a new review task is created.|
    |reviewapproval.css|This CSS file contains the styling of email templates.|


## Customize post-output generation workflow {#id17A6GI004Y4}

AEM Guides gives you the flexibility to specify a post-output generation workflow. You can perform some post-processing tasks on the output that gets generated using AEM Guides. For example, you might want to apply some CQ tags on the generated AEM Site output, or set certain properties on the PDF output, or you might want to send an email to a set of users once the output is generated.

You can create a new workflow model to use as a post-output generation workflow. When a post-output generation workflow is triggered, the output generation workflow shares contextual information through the workflow metadata map, which you can use to perform processing on the generated output. The following table describes the contextual information shared as metadata:

|Property|Type|Description|
|--------|----|-----------|
|``outputName``|String|Name of the output preset used to generate the output.|
|`generatedPath`|String|Path in DAM where the generated output is stored.|
|`outputType`|com.adobe.fmdita.output.OutputType|Type of the output preset.|
|`outputTitle`|String|Title of the output preset.|
|`outputHistoryPath`|String|Repository path of the history node.|
|`isSuccess`|Boolean|A flag depicting the final status of the output generation process - success or failure.|
|`logPath`|String|Path in DAM where the output generation logs are saved.|
|`generatedTime`|Long|Time at which the output generation process was triggered.|
|`initiator`|String|The user ID of the user who triggered the output generation workflow.|

To make use of the output generation metadata, you can create an ECMA script or an OSGi bundle. A sample of the ECMA script that uses the metadata is given below:

>[!NOTE]
>
> You can create this script in the ``/etc/workflows/scripts`` node.

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Once you have created the script, call the custom script in your workflow. Then, depending on your requirements, you can call the other workflow processes. Once you have designed your custom workflow, call the *Finalize Post Generation* as the last step in your workflow process. The *Finalize Post Generation* step ensures that the status of the output generation task gets updated to *Finished* on completion of the output generation process. After creating a custom post-output generation workflow, you can configure it with any of your output generation presets. Select the required workflow in the *Run Post Generation Workflow* property of the required preset. When you run an output generation task using the configured output preset, the task status \(in the Output tab\) changes to *Post-Processing*.

## Customize Update Asset workflow {#id18C3D0I0B5Z}

By default, the *DAM Update Asset* workflow triggers whenever you create or update any AEM Asset \(XML or non-XML\). For example, when you create a topic or update it, the *DAM Update Asset* workflow gets executed. The *DAM Update Asset* workflow tries to extract relevant metadata from the Assets. The out-of-box *Asset Update Workflow* does not have any steps to extract any relevant metadata from a DITA file and the *DAM Update Asset* workflow generates a lot of logs at the time of execution. If you want to avoid the extra logs, you can configure the workflow to skip all XML files from processing.

Perform the following steps to customize the *DAM Update Asset* workflow:

1.  open the **Workflow Launchers** page.

    The default URL to access the Workflow Launchers page is:

    ```http
    http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
    ```

1.  From the list of workflow launchers, open the properties of the **DAM Update Asset** workflow.

1.  Add a condition with the following expression:

    ```json
    jcr:content/metadata/dc:format!=application/xml
    ```

1.  Click **Save & Close**


## Configure post-processing XML workflow {#id18CJB03J0Y4}

AEM Guides creates a bunch of workflows that allow you to work with DITA content in AEM. For example, there are workflows that get executed when you upload DITA content or update existing content. These workflows parse DITA documents and perform various tasks such as setting the metadata, adding default output presets to new DITA maps, and other related tasks.

>[!NOTE]
>
> To customize or extend the default post-processing workflows, you can use the post-processing event handler described in the *API reference for Adobe Experience Manager Guides*.

The following properties govern how AEM Guides executes the post-processing workflows:

>[!NOTE]
>
> The following properties are accessible through the Web Console: http://<server name\>:<port\>/system/console/configMgr.

|Property|Bundle Name|Description|
|--------|-----------|-----------|
|Dynamic Outrefs

|`com.adobe.fmdita.postprocess.PostProcessObservation`

|For all files on which the post-processing has not been performed, it retrieves the outgoing references by parsing the topic files. It is recommended to keep this option disabled since it has a possibility of overloading the system if the number of files to be processed is large.

|
|Post Process Threads

|`com.adobe.fmdita.config.ConfigManager`

|Sets the number of post-processing threads to be used for post-processing workflow.

The default value is 1.

|

