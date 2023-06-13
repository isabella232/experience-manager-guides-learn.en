# Configure Translation feature in the Web Editor {#id21BONI0J0YR}

The Web editor provides a powerful translation feature to translate your content into multiple languages.

You can use the **Manage** tab in the Web Editor to translate your content. This tab is available by default.

To hide the **Manage** tab in the Web Editor, perform the following steps:

1.  Log into **Adobe Experience Manager** as an administrator.
1.  Click on the **Adobe Experience Manager** link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Click on **XML Editor Configuration**.
1.  Click on **Edit** icon on the top.
1.  Download the ui\_config.json file.Remove the following code snippet from the downloaded file:
1.  ```
{
						"component":"tab",
						"id":"workflow",
						"title":"Manage",
						"on-click":"APP_MODE_CHANGE",
						"items":[
						{
						"component":"label",
						"label":"Manage"
						}
						]
						},
```

1.  Upload the updated ui\_config.json file.

Note that the **Manage** filter is no longer available.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

