---
title: Pass on the metadata to the output using DITA-OT
description: Learn how to pass on the metadata to the output using DITA-OT publishing in AEM Guides.
---
# Pass on the metadata to the output using DITA-OT {#id21BJ00QD0XA}

Metadata is additional information about the output. In AEM Guides you can pass on the existing metadata or create custom metadata tags. You can pass on metadata to AEM, PDF, HTML5, EPUB, and Custom format outputs using DITA-OT publishing.

Perform the following steps to pass on the metadata to the output using DITA-OT publishing:

1.  In the **Assets UI**, navigate to and click on the DITA map file for which you want to pass the metadata to the DITA-OT.
1.  Select and edit an output preset to which you want to pass the metadata fields. For example, select PDF output preset.
1.  Select **DITA-OT** under Generate <output\> Using option in the selected output preset.

    ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1.  From the Properties drop down select the metadata that you want to pass to DITA-OT publishing.

    Properties dropdown lists both the custom and the default properties. For example, in the above screenshot author is the custom property while `dc:description`, `dc:language`, `dc:title`, and `docstate` are the default properties.

    >[!NOTE]
    >
    > These properties are picked from the metadataList file available at the following location:`/libs/fmdita/config/metadataList`. By default, there are four properties listed in this file- `dc:description`, `dc:language`, `dc:title`, and `docstate`.

    This file can be overlaid at: `/apps/fmdita/config/metadataList`.

    To pass a custom property for which you have already defined the values, see [Use AEM Metadata in DITA-OT PDF output](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1.  From the **Properties** dropdown, select the required custom and default properties. For example, select `author`, `dc:title`, and `dc:description`. These are the standard `metadata/properties` that gets created once we create a file. The selected properties are listed below the dropbox.

    ![](images/selected-metadata-properties.png){width="300" align="left"}

1.  Click **Done** on the top left to save the changes.
1.  Generate the output.

The selected metadata properties will be passed to the output generated using DITA-OT.

**Parent topic:**[Output generation](generate-output.md)
