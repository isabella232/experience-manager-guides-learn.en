# Configure text filters {#id21BPD0FK0XA}

AEM Guides provides the feature to search for text in the files present on the selected path of the AEM repository. You can use filter search to search files from the repository panel or to browse files. While working in the Web Editor, you need to use the file browse dialog to insert elements like image, reference, or key reference.

By default, you can use some enhanced filters to search the files in the AEM repository. You can filter all DITA Files or Non-DITA Files present on the selected path. You can also search for specific values in the attributes of DITA elements. You can also look for files which are checked out by the specified user.

>[!NOTE]
>
> You can also configure the global profile and add more filters for search.

Perform the following steps to configure the text filters:

1.  Log into Adobe Experience Manager as an administrator.
1.  Click on the**Adobe Experience Manager** link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Click on **XML Editor Configuration**.
1.  Click on **Edit** icon on the top.
1.  Download the ui\_config.json file.
1.  Configure the filters in the file. You can also add custom filters as shown in the example below:

    The following code snippet shows how to add filtering options DITA Files, Non-DITA, DITA Elements and Checked out by Files. It also contains a custom filter -Tags.

    ```json
    [
      {
        "title": "DITA files",
        "property": "jcr:content/metadata/dita_class",
        "operation": "like",
        "children": [
          {
            "title": "DITA Topics",
            "value": "- topic/topic",
            "checked": true
          },
          {
            "title": "DITA Maps",
            "value": "- map/map",
            "checked": true
          }
        ]
      },
      {
        "title": "DITA elements",
        "property": "jcr:content/ditameta",
        "widgetId": "dita_filter",
        "operation": "like"
      },
      {
        "title": "Checked out by",
        "property": "jcr:content/cq:drivelock",
        "operation": "like",
        "itemConfig": {
          "component": "textfield",
          "placeholder": "Checked out by"
        },
        "children": [
          {
            "title": "Check out"
          }
        ]
      },
      {
        "title": "Tags",
        "property": "jcr:content/metadata/cq:tags",
        "itemConfig": {
          "component": "textfield",
          "placeholder": "Enter Tag"
        },
        "children": [
          {
            "title": "Tags"
          }
        ]
      }
    ]
    ```

    In the above code snippet, the first filter is for DITA Files. The filter definition takes the following parameters:

    ****Title****: The display name of the filter. This title appears as the filtering option in the file browse dialog.

    ****Property****: The property to match in the file's metadata. For example, to allow only those files that have the dita\_class metadata in their property, the property filter takes "jcr:content/metadata/dita\_class" as its value.

    ****Operation**:** Specify "exists" to match for existence of the value specified in the property parameter

1.  Upload the updated ui\_config.json file which contains the added filters.

The configured filters are available in the filters panel.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)

