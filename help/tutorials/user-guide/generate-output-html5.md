# HTML5 {#id205BE700XO1}

The HTML5 output is generated in a flat folder hierarchy. This implies that the folder structure used by the content in the repository is not replicated in the HTML5 output. The entire content is published in HTML5 output format and saved in a single folder. The file names are also replaced with the UUIDs of the files in the generated output. The only file that doesn't have a UUID-based filename is the index.html file.

You can create the HTML preset in two ways:

**From the Web Editor:** In the Repository panel, open the DITA map file in Map View, then in the Output tab, select the + icon to create an output preset, and then select HTML5 from the type drop-down in the Add preset dialog.

>[!NOTE]
>
> You can choose the method to generate HTML5 using the DITA-OT or FMPS \(if your system administrator has configured it\).

In the Web editor the configurations have been organized under General and Advanced tabs:

**General**

The **General** tab contains the following configurations:

-   Output Path
-   DITA-OT Command Line Arguments
-   File Name
-   Apply Conditions Using \(If the conditions are defined for a map\)
-   Use Baseline \(If a baseline is created for a map\)
-   Post Generation Workflow

**Advanced**

The Advanced tab contains the following configurations:

-   Transformation Name
-   Clean DITA-OT Temporary Files
-   Properties

For details, refer to [HTML5 configuration](#id231KJA00REJ).

**From the map dashboard**

To open output presets for PDF, click on a DITA map file from the Assets UI, then click on Output Presets, and then click on the HTML5 option. In the Map dashboard, click **Edit** on the top to update the various configurations, and then click **Save**.

**HTML5 configuration**

The following options are available for the HTML5 output:

|HTML5 options|Description|
|-------------|-----------|
|Output Type|The type of output you want to generate. To generate HTML5 output, choose the HTML5 option.|
|Setting Name|Give a descriptive name for the HTML5 output settings you are creating. For example, you can specify *Internal customers output* or *end-users output*.|
|DITA-OT Command Line Arguments|Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, see [DITA-OT documentation](https://www.dita-ot.org/).|
|Generate Responsive Using|Select DITA-OT to generate the HTML5 output.|
|Apply conditions using|Select one of the following options:-   **None applied:** Select this option if you do not want to apply any condition on the published output.
-   **DITAVal file**: Select DITAVal file\(s\) to generate personalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you have selected any other file type. FrameMaker Publishing Server doesn't support multiple DITAVAL files.
-   **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#).
 You can select multiple DITAVAL files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVAL files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only save DITAVAL files. An error is displayed if you have selected any other file.>
**NOTE**_FrameMaker Publishing Server doesn't support multiple DITAVAL files._|
|Transformation Name|Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, see [DITA-OT transformations \(output formats\)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide.|
|File Name|Specify the file name with which you want to save the HTML5 output. **Note:** If you do not provide a file name, then the DITA map's title is used to generate the final HTML5 output file name. If the map does not have a title, then the DITA map's file name is used to name is the final HTML5 output. The file name is sanitized using the rules configured in the system to handle any invalid character.|
|Run Post Generation Workflow|When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.
**NOTE** _For more information about creating a custom post-output generation workflow, see *Customize post-output generation workflow* in Install and configure Adobe Experience Manager Guides as a Cloud Service._|
|Destination Path|The path within your AEM repository where the HTML5 output is stored.|
|Clean DITA-OT Temporary Files|Select this option to clean the temporary files generated by DITA-OT. The location where DITA-OT stores temporary files can be found in the output generation log.
If you are experiencing errors while generating output through DITA-OT, you can deselect this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.|
|Use Baseline|If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.
See [Work with Baseline](generate-output-use-baseline-for-publishing.md#) for more detail.|
|Properties|Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties that you select from the drop-down list are listed below the **Properties** field and are removed from the drop-down list. Once set, these properties are also copied into the topics within the map. **Note:** You can also pass on the metadata to the output using DITA-OT publishing. For more details see, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#).|

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)

