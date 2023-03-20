---
title: AEM Site
description: Learn how to AEM Site
---

# AEM Site {#id205BE3008SW}

The following options are available for the AEM Site output:

You can create the AEM site preset in two ways:

**From the Web Editor:** In the Repository panel, open the DITA map file in Map View, then in the Output tab, select the + icon to create an output preset, and then select AEM Site from the type drop-down in the Add preset dialog.In the Web editor the configurations have been organized under General and Advanced tabs:

**General**

The **General** tab contains the following configurations:

- Site Name
- Output Path
- Existing Output Pages
- Delete Orphan Site Pages
- Apply Conditions Using \(If the conditions are defined for a map\)
- Use Baseline \(If a baseline is created for a map\)
- Post Generation Workflow

**Advanced**

The Advanced tab contains the following configurations:

-   Clean DITA-OT Temporary Files
-   Generate Separate PDF for Every Topic
-   Use Map properties as Default

For details, refer to [AEM Site configuration](#id231KIM004X1).

**From the map dashboard**

To open output presets for AEM Site, click on a DITA map file from the Assets UI, then click on Output Presets, and then click on the AEM Site output option.In the map dashboard, click **Edit** on the top to update the various configurations, and then click **Save**.

    >[!TIP]
    >
    > See the *AEM Site publishing* section in the Best practices guide for best practices around creating AEM Site output.

**AEM Site configuration**

The following options are available for the AEM Site output:

| AEM Site options | Description |
| --- | --- |
| Output Type | The type of output you want to generate. To generate responsive AEM Site output, choose the AEM Site option. |
| Setting Name | Give a descriptive name for the AEM site settings you are creating. For example, you can specify _Internal customers output_ or _end-users output_. |
| Site Name | A site name where the output is stored in your AEM repository.<br><br>A node in the AEM repository is created with the name specified here. If you do not specify the Site Name, then the site node is created with the DITA map file name.<br><br>The Site Name you specify here is also used as the title in the browser tab.<br><br>You can also use variables while setting the Site Name. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Select the design template that you want to use to generate the output.<br><br>For details about how to use custom design templates to generate output, contact your publishing administrator. |
| Destination Path | The path within your AEM repository where the output is stored. While generating the final output, the Site Name and Destination Path are combined. For example, if you specify the Site Name as `user-guide` and the Destination Path as `/content/output/aem-guides`, then the final output is generated under the `/content/output/aem-guides/user-guide` node.<br><br>You can also use variables while setting the Destination Path. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| Apply Conditions Using | Select one of the following options:<br><br>* None Applied: Select this option if you do not want to apply any condition on the published output.<br>* DITAVal file: Select DITAVal file(s) to generate conditionalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you select any other file type.<br>* Condition preset: Select a condition preset from the drop-down to apply a condition while publishing the output. This option is visible if you have added a condition for the DITA map file. The conditional settings are available in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Existing Output Pages | Select the Overwrite Content option to overwrite content in the existing pages. This option only overwrites content present under the content and head nodes of the page. This option enables blended publishing of content. Selecting this option provides an option to select deleting orphan pages from the published output. This is also the _default_ option for creating the AEM Site output.<br><br>Select the Delete and Create option to force delete any existing pages during publishing. This option deletes the page node along with its content and all child pages under it. Use this option if you have changed the design template of your output preset or if you want any extra pages already present in the destination to be removed. |
| Delete Orphan Site Pages | Selecting the Overwrite Content in the Existing Output Pages setting presents this option. If you select this option, then all orphan pages are deleted from the published AEM Site. For this feature to run successfully, you must publish the entire DITA map and not use the incremental publishing.<br><br>Let's say you have published a DITA map, which contains topics a.dita, b.dita, and c.dita. Before publishing the map again, you removed b.dita topic from the map. Now, if you have selected this option, then all content related to b.dita is removed from the AEM Site output and only a.dita and c.dita are published.<br><br>This feature does not remove any published child map. For example, if your parent map contains a child map, and you remove the entire child map, then the child map content is not deleted from the published output. However, if you remove any topic from a child map and republish, then the removed topic's content is deleted from the site output.<br><br>Also, if there is any referenced content, and that content is removed before republishing, then the referenced content's data is not removed.<br><br>Note: Information about deleted orphan pages is also captured in the output generation logs. For more information about accessing the log files, see [View and check the log file](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Clean DITA-OT Temporary Files | Select this option to clean the temporary files generated by DITA-OT. The location where DITA-OT stores temporary files can be found in the output generation log.<br><br>If you are experiencing errors while generating output through DITA-OT, you can deselect this option to retain the temporary files. You can then use those files to troubleshoot output generation errors. |
| Generate Separate PDF for Each Topic | If selected, a PDF is also created for every topic in the DITA map. When you choose this option, a new Split PDF Path option is displayed.<br><br>In the Split PDF Path field, specify the path to store the PDFs generated for each topic.<br><br>Note: AEM Guides uses the DITA-OT plug-in named pdfx to generate PDF for each topic. This plug-in is bundled with the DITA-OT package shipped out-of-the-box. You can customize this plug-in to generate PDF as per your requirements. If you use a custom DITA-OT plug-in, ensure that you integrate the pdfx plug-in to have topic-level PDF generation capability. |
| Run Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>Important: When you are generating incremental output for the AEM Site, then the output is created using the current version of the files and not the attached Baseline.<br><br>See [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties that you select from the drop-down list are listed below the Properties field and are removed from the drop-down list.<br><br>Note: The metadata properties are case-sensitive.<br><br>* If you have selected a Baseline, then the values for the properties are based on the version of the selected Baseline.<br>* If you have not selected a Baseline, then the values for the properties are based on the latest version.<br><br>You can also pass on the metadata to the output using DITA-OT publishing. For more details see, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>Note: If you have not defined the `cq:tags` in the Properties option, then the values for `cq:tags` are picked from the current working copy even if you have selected a Baseline for publishing. |
| Use Map Properties If Its Missing On Topic | If selected, the properties defined for the map file are also copied into the topics where such properties are not defined. Consider the following points while using this option:<br><br>* Only String, Date, or Long (singe and multi-valued) properties can be passed on to the AEM Site pages.<br>* The metadata values for a String type property does not support any special characters (such as @, #, " ").<br>* This option should be used along with the Properties option. |

## Additional note on AEM Site 

**Generate article-based output from the Web Editor**
You can generate the AEM Site output for one or more topics, or the entire DITA map from the Web Editor. You need to create output presets for your DITA map and then you can easily generate the AEM Site output for your map. If you have updated a few topics in your map, you can also generate the AEM Site output only for those topics from the Web Editor. For more details, see [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

**Generate output linking topics from other maps**
It is a very common scenario to have a large set of documentation spread across multiple folders and DITA maps. It becomes extremely complex to publish content that is linked from various places. By default, all links `xref` are created with the `local` `@scope`. Publishing such topics does not involve any challenge, as it uses direct link to the topic. In case the topic is outside the current DITA map, the link does not show the linked content.

    Another way of linking content is to create a link using the `peer` `@scope`. For such content, the link is resolved at run-time by picking the configured context for the linked topic from the DITA map's publishing context. The following screenshot shows the Properties panel for a link that has the `peer` `@scope`:

    ![](images/peer-link-scope-link.png)

    To simplify publishing of complex maps and topics that link to other topics in other maps, AEM Guides allows you to set the publishing context for each output preset.

    The publishing context allows you to specify which topic has to be used from which map for publishing a specific output. Let's understand this with the help of an example — let's say you have four folders: sample a, sample b, sample c, and sample d. Each folder contains a DITA map — DITA map A, DITA map B, DITA map C, and DITA map D. Cross-map linking will happen when a topic in DITA map A links to a topic in DITA map B, C, or D. In the following screenshot, a sample concept topic contains links \(or references\) to files that are a part of other DITA maps.

    ![](images/sample-concept-link-to-other.png)

    Now, when you configure the AEM Site publish settings for the map file that contains this topic, you can select which publishing context for the linked content is used while publishing. A publishing context is a combination of DITA map and its output preset. The output preset, in turn, contains a specific version of the content and conditional presets. This entire combination of the DITA map, output preset, \(files\) version, and conditions define the publishing context for a linked map.

    Perform the following steps to specify the publishing context for cross-linked files:

    1.  Open the **Output Presets** tab of the DITA map you want to publish.

    1.  Select the **AEM Site** output preset.

        You get the AEM Presets Settings and Publish Context tabs.

        ![](images/aem-site-publish-settings.png)

    1.  Open the **Publish Context** tab.

        You are shown a list of dependent topics. These are the topics that are linked from some topic in the current map, but they are available in some other DITA maps.

        >[!NOTE]
        >
        > The Publish Context tab shows topics that are linked using the `peer` `@scope` only. For links with `local` `@scope`, you don't need to specify the publishing context.

        By default, all linked topics have their latest output preset and map selected.

        ![](images/default-publish-context.png)

    1.  To change the default selection of DITA map and preset, click **Edit** \(in the main toolbar\).

    1.  If you want to use the most recently published output of each dependent file in the map, select **Use most recently generated publish context for all dependent topics**.

    1.  In the **Parent Map** drop-down list, select the map file with whose output you want to link the current map's output.

        On selecting a map file, the map's UUID is shown in the Parent Map UUID column. The Output Presets associated with the selected map are listed in the Parent Map's Preset list.

    1.  In the **Parent Map's Preset** drop-down list, select the output preset that you want to link the current map's output with.

    1.  Select the required map and its output preset for all dependent topics and click **Done**.
        
        The context for the dependent topics is now set. You can generate the output for the current map. For more information about generating output, see [Generate output for a DITA map from the map console](generate-output-for-a-dita-map.md#).

**Blended publishing**
AEM Guides supports publishing DITA content within your existing AEM site. For example, if you have an existing site, you can use the AEM Site output to publish only the DITA content on that site. In this process, the existing non-DITA content is not modified by the publishing process. For more information about setting up your site to publish only DITA content, contact your publishing administrator.

**Publishing `conref`**
If you are using `conref` in your content, then it is published as normal or embedded content along with the content in the source \(or referring\) topic. The `conref` content is rendered along with the main content and no separate site page is created for the same. When you search for the content that is referred in the `conref`, then only the main topic or page containing the `conref` content is shown in the search results.

    >[!NOTE]
    >
    >If you have generated separate pages for the `conref` content using AEM Guides version 3.5 or earlier, then it is recommended to clean/delete those pages by using the [Delete Orphan Site Pages](#delete-orphan-page-aem-site) option.

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)

