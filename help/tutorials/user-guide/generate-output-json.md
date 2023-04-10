---
title: JSON
description: Learn how to use JSON
---

# JSON {#id231KK0180T4}

You can create the JSON preset from the Web Editor:

In the Repository panel, open the DITA map file in Map View, then in the Output tab, select the + icon to create an output preset, and then select JSON from the type drop-down in the Add preset dialog.

In the Web editor, the following configurations have been organized under the **General** tab:

-   Output Path
-   Index File
-   Apply Conditions Using \(If the conditions are defined for a map\)
-   Use Baseline \(If a baseline is created for a map\)
-   Properties to Propagate in the Output
-   Post Generation Workflow

For details, refer to [JSON configuration](#id231KJA00REJ).

**From the map dashboard**

To open output presets for PDF, click on a DITA map file from the Assets UI, then click on Output Presets, and then click on the HTML5 option. In the Map dashboard, click **Edit** on the top to update the various configurations, and then click **Save**.

**JSON configuration**

The following options are available for the JSON preset:

>[!NOTE]
>
> You can also edit the JSON file in the Web Editor.

| JSON output options | Description |
| --- | --- |
| Output Path | The path within your AEM repository where the JSON output is stored. |
| Index File | You can give a name for the index file you're creating for the JSON output. By default, it picks the DITA map's file name and adds a suffix (like `map_filename_index.json`).<br><br>You can also use variables while setting the Index File. For more details about using variables, see [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| Apply conditions using | Select one of the following options:<br><br>* **None applied**: Select this option if you do not want to apply any condition on the published output.<br>* **DITAVAL file**: Select DITAVAL file(s) to generate personalized content. You can select multiple DITAVAL files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVAL files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVAL file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVAL files and an error is displayed if you have selected any other file type.<br>* **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>See [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| Properties to Propagate in the Output | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties that you select from the drop-down list are listed below the Properties field.<br><br>**Note**: You can also define custom properties and pass on the metadata to the output using DITA-OT publishing. For more details see, [Work with metadata](metadata-dita.md#id21BJ00QD0XA). |
| Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.<br><br>**Note**: For more information about creating a custom post-output generation workflow, see _Customize post-output generation workflow_ in the Install and configure Adobe Experience Manager Guides as a Cloud Service guide. |

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)

