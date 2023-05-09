# Open DITA topic or map files in same tab {#id223HI0P202H}

In some workflows, when you click on a link of a topic or a map file, it opens in a new tab. This could lead to many tabs opened in your browser, which could impact your productivity. You can change this behavior of opening a topic or map file in a new tab, and force it open in the current tab itself. To do so, perform the following configuration changes:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Open DITA Topic/Map in Same Tab** option.

1.  Click **Save**.


This setting impacts the following places from where you can access the topic or map files:

-   Create DITA Topic \(at the end of the workflow, when you click the **Open Topic** button\)

-   Create DITA Map \(at the end of the workflow, when you click the **Open Map** button\)

-   Topics tab in the DITA map console

-   Baselines tab in the DITA map console

-   Reports tab in the DITA map console


**Parent topic:**[Customize Web Editor](conf-web-editor.md)

