---
title: Configure default value for the Tags View
description: Learn how to Configure default value for the Tags View
---

# Configure default value for the Tags View {#id223GN0M0NDC}

AEM Guides allows you to configure the default state for the Tags View in the Web Editor, which helps you to keep the Tags View on or off by default for a new user's session.Perform the following steps to configure the default value for Tags View:

1.  Download the UI configuration file by logging into Adobe Experience Manager as an administrator.
1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click the **Edit** icon on the top.
1.  In the **XML Editor UI configuration** section, click the **Download** icon to download the `ui_config.json` file on your local system.
1.  In the `ui_config.json` file, change the default tags view state by changing the defaultValues section as shown below:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Save the file and upload it.

>[!NOTE]
>
> The user's preference in the Web Editor to enable/disable the Tags View has precedence over this default value. So, if a user enables the Tags View from the Web Editor, it remains enabled even across the sessions.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

