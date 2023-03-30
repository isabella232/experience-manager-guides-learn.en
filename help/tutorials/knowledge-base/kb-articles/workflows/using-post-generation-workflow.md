---
title: Post Generation Workflow
description: An overview of post generation workflow with an example
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
---
# AEM Guides publishing - Post Generation Workflow

AEM Guides gives you the flexibility to specify a post-output generation workflow. You can perform some post-processing tasks on the output that gets generated using AEM Guides.
For example, you might want to set certain properties on the PDF output, or you might want to send an email to a set of users once the output is generated.


## What are the steps involved to utilize Post generation workflows

### Create a workflow process 

Create a Java or ECMA based workflow process that performs the operation on the generated output. For example, copying some metadata from source to the generated content or manipulating metadata of the generated output.
- We will take and example of creating such a process using ECMA script (you can refer attached package)
- For Java based workflow process, refer section "*Customize post-output generation workflow*" of [Installation and configuration guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Create a workflow model

With the custom workflow process that you created in previous step, create a workflow model and add that process step to it. 
- You need to also add a mandatory process step "*Finalize Post Generation*" as the last step of the workflow. 

Refer sample workflow model shown below:

![Post generation workflow model](../assets/workflows/pgwf-workflow-model.png)


### Use this post generation workflow on a map

Post generation workflow is a property that can be configured on any output preset within AEM Guides publishing mechanism. Example:

![Post generation workflow on Output Preset](../assets/workflows/pgwf-preset-settings.png)


Assuming the selected model is already created.


### Testing

Now you can run the publishing using this preset and validate the process step output


## Sample

For your reference, you can use below package and install it via package manager to test the sample post generation workflow (*as referred in screenshots above*)

[A sample ECMA based post generation workflow model](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
