---
title: Configure title for Cehck in and Check out icons
description: Learn how to configure the title for Check in and check out icons
---
# Configure the title for Check in and Check out icons

AEM Guides allows you to configure the title for Check in and Check out icons in the Web Editor. Perform the following steps to configure the title for Check in and Check out icons:

1.  Download the UI configuration file by logging into Adobe Experience Manager as an administrator.
1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click the **Edit** icon on the top.
1.  In the **XML Editor UI configuration** section, click the **Download** icon to download the `ui_config.json` file on your local system.
1.  In the `ui_config.json` file, change the title  in the "topbar" section. You can change the following values:

    ```json
    //Change title to "Check out" instead of "Lock"
            "title": "Check out"

    //Change title to "Check in" instead of "@checkOutBy
             "title": "Check in"
    ```

1. Save the file and upload it.

