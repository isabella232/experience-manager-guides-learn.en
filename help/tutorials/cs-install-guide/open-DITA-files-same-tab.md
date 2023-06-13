# Open DITA topic or map files in same tab {#id223HH0301J3}

In some workflows, when you click on a link of a topic or a map file, it opens in a new tab. This could lead to many tabs opened in your browser, which could impact your productivity. You can change this behavior of opening a topic or map file in a new tab, and force it open in the current tab itself.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to open a topic or map file in a new tab:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.openinsametab`|Boolean \(true/false\).

**Default value**: `false`

|

This setting impacts the following places from where you can access the topic or map files:

-   Create DITA Topic \(at the end of the workflow, when you click the **Open Topic** button\)

-   Create DITA Map \(at the end of the workflow, when you click the **Open Map** button\)

-   Topics tab in the DITA map console

-   Baselines tab in the DITA map console

-   Reports tab in the DITA map console


**Parent topic:**[Customize Web Editor](conf-web-editor.md)

