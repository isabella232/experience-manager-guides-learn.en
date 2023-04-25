---
title: Use variables for setting the Destination Path, Site Name, or File Name options
description: Learn how to Use variables for setting the Destination Path, Site Name, or File Name options
exl-id: e8d5b7c7-4f80-4ab6-9ad1-308bf0d4cf74
---
# Use variables for setting the Destination Path, Site Name, or File Name options


While generating outputs in AEM Site or PDFs, you can use variables to define the Destination Path, AEM Site Name, or PDF File Name options. You can use a single or a combination of variables to define theses options.

The following table lists the variables that are supported out of the box:

| Variable | Final Destination Path | Example |
| --- | --- | --- |
| `${map_filename}` | Uses the DITA map files name to create the destination path. | **DITA map file name**:<br>`AEMGuides.ditamap`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_filename}`<br><br>**Final output location**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Uses the DITA map title to create the destination path. | **DITA map file name**:<br>`AEMGuides.ditamap`<br><br>**DITA map Title**:<br>`AEMGuides`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_title}`<br><br>**Final output location**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Uses the output preset name to create the destination path. | **Output Preset Name**:<br>`AEM Guides PDF Output`<br><br>**DITA map file name**:<br>`SampleDita.ditamap`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${preset_name}`<br><br>**Final output location**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Uses the language code where the map file is located to create the destination path. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${language_code}`<br><br>**Final output location**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Uses the complete path of the map file to create the destination path.<br><br>**Note**:This variable cannot be used to specify the AEM Site Name or PDF File Name. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_parentpath}`<br><br>**Final output location**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Uses the path of the map file after the language folder to create the destination path.<br><br>**Note**: This variable cannot be used to specify the AEM Site Name or PDF File Name. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Final output location**:<br>`/content/output/sites/user-guide/SampleDita.html` |

In addition, you can also use the metadata defined for the DITA map or bookmap file as variables. The metadata can be found under the `/jcr:content/metadata` node of the DITA map or bookmap file. For example, one of the metadata properties define in the `/jcr:content/metadata` node is `dc:title`. You can specify `${dc:title}` and the title value is used in the final output.
**Parent topic:**[Output generation](generate-output.md)
