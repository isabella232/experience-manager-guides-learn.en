---
title: Configure single topic PDF generation
description: Learn how to Configure single topic PDF generation
---
# Configure single topic PDF generation {#id22ADC70M0XA}

With the AEM Guides, you can generate the PDF of individual topics or an entire map file. You can publish your topics in a PDF format using native PDF or DITA-OT method. Use native PDF method to generate a feature-rich PDF output based on W3C CSS3, and CSS paged media standards. You can use the DITA-OT method to generate a PDF output for a map from the map dashboard.

>[!NOTE]
>
> Native PDF is the default method to generate a PDF in the current version of AEM Guides.

To enable the old PDF generation via the DITA-OT from the topic preview mode, perform the following steps:

1.  Log into Adobe Experience Manager as an administrator and download the UI configuration file.

1.  To do so, click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click **Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system. You can then make changes to the file and then upload the same.
1.  In the `ui_config.json` file, find the following configuration:

    ```
    {
                            "component": "button",
                            "variant": "action",
                            "quiet": true,
                            "icon": "filePDF",
                            "title": "Download as PDF",
                            "on-click": "EDITOR_SAVE_AS_PDF"
                            }
    ```

    and replace it with

    ```
    {
                            "component": "button",
                            "icon": "filePDF",
                            "variant": "action",
                            "quiet": true, "title": "Export as PDF",
                            "on-click": "DOWNLOAD_TOPIC_PDF",
                            "show" : ["@isPreviewMode", "@isXmlMode"]
                            }
    ```

1.  Save the file and upload it.

After performing the above given steps, if you choose the same folder profile from User Preferences in the Web Editor, you will then see the option for PDF generation in the preview mode of a topic.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
