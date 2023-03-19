# PDF {#id205BE600HAH}

You can create the PDF preset in two ways:

**From the Web Editor:** In the Repository panel, open the DITA map file in Map View, then in the Output tab, select the + icon to create an output preset, and then select PDF from the type drop-down in the Add preset dialog.

>[!NOTE]
>
> You can choose the method to generate PDF using the DITA-OT, Native PDF, or FMPS \(if your system administrator has configured it\).

In the Web editor the configurations have been organized under General and Advanced tabs:

**General**

The **General** tab contains the following configurations:

-   Output Path
-   DITA-OT Command Line Arguments
-   Transformation Name
-   PDF Filename
-   Apply Conditions Using \(If the conditions are defined for a map\)
-   Use Baseline \(If a baseline is created for a map\)
-   Post Generation Workflow

**Advanced**

The Advanced tab contains the following configurations:

-   Enable Versioning
-   Clean DITA-OT Temporary Files

For details, refer to [PDF configuration](#id231KIM004X1).

**From the map dashboard**

To open output presets for PDF, click on a DITA map file from the Assets UI, then click on Output Presets, and then click on the PDF option. In the Map dashboard, click **Edit** on the top to update the various configurations, and then click **Save**.

**PDF configuration**

The following options are available for the PDF Output:

|PDF options|Description|
|-----------|-----------|
|Output Type|The type of output you want to generate. To generate PDF output, choose the PDF option.|
|Setting Name|Give a descriptive name for the PDF output settings you are creating. For example, you can specify *Internal customers output* or *end-users output*.|
|DITA-OT Command Line Arguments|Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, see [DITA-OT documentation](https://www.dita-ot.org/).

|
|Apply conditions using|Select one of the following options:-   **None applied**: Select this option if you do not want to apply any condition on the published output.
-   **DITAVal file**: Select DITAVal file\(s\) to generate personalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you have selected any other file type. FrameMaker Publishing Server doesn't support multiple DITAVAL files.
-   **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#).

|
|Generate PDF Using|Select DITA-OT to generate the PDF.|
|Run Post Generation Workflow|When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.

>[!NOTE]
>
> For more information about creating a custom post-output generation workflow, see Customize post-output generation workflow in Install and configure Adobe Experience Manager Guides as a Cloud Service.

|
|Transformation Name|Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, see [DITA-OT transformations \(output formats\)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide.|
|File Name|Specify the file name with which you want to save the PDF. You can also use variables while setting the PDF File Name. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#).

>[!NOTE]
>
> If you do not provide a file name, then the DITA map’s title is used to generate the final PDF’s file name. If the map does not have a title, then the DITA map’s file name is used to name is the final PDF. The file name is sanitized using the rules configured in the system to handle any invalid character.

|
|Destination Path|The path within your AEM repository where the PDF is stored. You can also use variables while setting the Destination Path. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#).

|
|Clean DITA-OT Temporary Files|Select this option to clean the temporary files generated by DITA-OT. The location where DITA-OT stores temporary files can be found in the output generation log.

If you are experiencing errors while generating output through DITA-OT, you can deselect this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.

|
|Use Baseline|If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.

See [Work with Baseline](generate-output-use-baseline-for-publishing.md#) for more detail.

|
|Properties|Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties that you select from the drop-down list are listed below the **Properties** field and are removed from the drop-down list. Once set, these properties are also copied into the topics within the map.**Note:** You can also pass on the metadata to the output using DITA-OT publishing. For more details see, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#).

|

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)

