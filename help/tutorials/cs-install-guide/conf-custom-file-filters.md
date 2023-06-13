# Configure filters for file browse dialog {#id20CIL7009GN}

While working in the Web Editor, you need to use the file browse dialog to insert elements like image, reference, or key reference. The default file browse dialog does not offer any file filtering option. You can add your own filters that would allow you to access the required files easily and quickly.

Perform the following steps to add your custom file filtering options to the file browse dialog:

1.  To download the UI configuration file log into Adobe Experience Manager as an administrator.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click **Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system. You can then make changes to the file and then upload the same.
1.  In the `ui_config.json` file, add the definition of the filters you want to add.

    The following code snippet shows how to add two filtering options — DITA Files and Image Files.

    ```
    "browseFilters": [
    					{
    					"title": "DITA Files",
    					"property": "jcr:content/metadata/dita_class",
    					"operation": "exists"
    					},
    					{
    					"title": "Image Files",
    					"property": "jcr:content/metadata/dc:format",
    					"value": [
    					"image/jpeg",
    					"image/gif",
    					"image/png"
    					]
    					}
    					]
    ```

    In the above code snippet, the first filter is for DITA Files. The filter definition takes the following parameters:

    title
    :   The display name of the filter. This title appears as the filtering option in the file browse dialog.

    property
    :   The property to match in the file's metadata. For example, to allow only those files that have the `dita_class` metadata in their property, the property filter takes " `jcr:content/metadata/dita_class`" as its value.

    operation
    :   Specify " `exists`" to match for existence of the value specified in the property parameter.

    The second filter is for Image Files. The parameters are similar to the first filter except the `value` parameter. The `value` parameter takes an array of image types as its value. All file types specified in the value parameter are searched for and shown in the file browse dialog, all other file types are ignored.

1.  Save the *ui\_config.json* file and upload the same. Then, reload the Web Editor.

    When you launch the file browse dialog, the filter options configured in the ui\_config.json file are shown.

    ![](assets/file-browse-custom-filters.png)


**Parent topic:**[Customize Web Editor](conf-web-editor.md)

