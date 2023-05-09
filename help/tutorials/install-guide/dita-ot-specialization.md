# Use custom DITA-OT and DITA specialization {#id181GAJ0005Z}

The DITA Open Toolkit \(DITA-OT\) is a set of Java-based, open-source tools that provide processing for DITA maps and topic content. AEM Guides allows you to easily import and use custom DITA-OT plug-ins. Once imported, AEM Guides can be configured to use the custom DITA-OT plug-in to generate output in any format. At the time of generating the output, simply select the DITA-OT option and AEM Guides uses the custom DITA-OT plug-in to generate the required output.

If you want to process Ant parameters while publishing any output, AEM Guides gives you an easy way to do so. You can specify which Ant parameters you want to use and the same are then processed by the publishing process.

>[!NOTE]
>
> AEM Guides is shipped with DITA-OT version 3.3.2. However, AEM Guides supports DITA-OT version 1.7 and above. For the complete list of DITA-OT versions, see [DITA-OT versions](http://www.dita-ot.org/download).

>[!TIP]
>
> See [appendix.md\#](appendix.md#)the *DITA-OT Profiles configuration* and *Using custom DITA-OT*[appendix.md\#](appendix.md#) sections in the Best practices guide for best practices around using custom DITA-OT plug-ins.

## Use custom DITA-OT plug-ins {#id181NH1020L7}

There are two ways to use custom DITA-OT plug-in for publishing. First method is to upload the custom DITA-OT plug-in into the AEM repository. The other method is to save the custom DITA-OT plug-in on your server, create a Profile and provide the location of the custom DITA-OT plug-in in your Profile.

By default, AEM Guides comes with a pre-configured Profile that contains the configurations for the default templates to use for editing and publishing content. You can create custom profiles with custom templates to be used while editing documents and custom DITA-OT plug-ins to publish content.

The default DITA-OT package available with AEM Guides comes with Apache FOP XSL-FO processor, which does not support rendering of MathML equations. If you are using MathML equations in your content, then ensure that you have integrated a MathML rendering engine plug-in for Apache FOP or use a different XSL-FO processor.

>[!IMPORTANT]
>
> If you have upgraded AEM Guides from version 2.2 to 2.5.1 or 2.6, then all changes made through the configuration manager are automatically picked and stored in the Default Profile.

Perform the following steps to upload custom DITA-OT plug-in into the AEM repository:

1.  Log into AEM and open the CRXDE Lite mode.

1.  Download the `DITA-OT.ZIP` file.

    The location of the `DITA-OT.ZIP` file is `/libs/fmdita/dita_resources/DITA-OT.zip`.

    ![](assets/dita-ot-zip-in-crx.png)

1.  Extract the contents of the zip file on your server.

1.  Use a DITA-OT plug-in integrator mechanism to integrate the new version of DITA-OT with your custom DITA-OT plug-in.

    >[!NOTE]
    >
    > The class path separator in the plug-in ZIP file is operating system-dependent, which means if your server is hosted on Windows then the class path separator will be different from the one used on Linux. For more information about manually integrating plug-ins, see the *Manually installing plug-ins* topic in DITA-OT documentation.

1.  Create the ZIP file again keeping the same name \(`DITA-OT.ZIP`\) and the folder structure.

1.  Upload the updated ZIP file back into the AEM repository.

    Ensure the following checks before uploading the ZIP file:

    -   Run the integrator \(to install the custom plugin\) on a Mac/Linux OS to avoid issues with file separators - as Windows and Linux OS have different file separators, the plugin integrated on Mac/Linux OS is compatible with both Windows and Linux setup.
    -   Ensure that the `DITA-OT.ZIP` file contains a folder named "DITA-OT" which has all the relevant plugins and files.
    -   Check that `DITA-OT.ZIP` file you create is of mimeType: "nt:file" \(this corresponds to the primary type of ZIP file when uploaded to AEM\). Use a WebDAV tool or code deployment to upload this ZIP file to the desired path in AEM. \(Do not use AEM's package manager to deploy this ZIP file as this ZIP is not an AEM content package but just an archive file.\)
    >[!NOTE]
    >
    > It is recommended not to overwrite the default DITA-OT package. You should upload your custom DITA-OT package containing your plug-in at some other location under the `apps` folder.

1.  Open the default DITA Profile for editing and save it \(without making any updates\) for the changes to take effect.


Perform the following steps to create a new profile and configure it to use custom DITA-OT plug-in stored on your server:

1.  Store the custom DITA-OT plug-in on your server.

    >[!NOTE]
    >
    > The folder structure for storing the custom DITA-OT plug-in should be: `\*<parent-folder\>*\DITA-OT`.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Click on the **DITA Profiles** tile.

    >[!NOTE]
    >
    > The Default Profile information is displayed on the Profiles page. If you have upgraded AEM Guides from version 2.2 to 2.5.1 or 2.6, then all changes made through the configuration manager are automatically picked and stored in the Default Profile.

1.  You can choose to edit the Default Profile, create a new profile, or duplicate settings from the Default Profile to create a new profile.

    >[!NOTE]
    >
    > You can update the Default profile, but you cannot delete it. However, all new profiles that you create can be edited and deleted.

1.  Configure the following properties to use the custom DITA-OT plug-in:

    |Property name|Description|
    |-------------|-----------|
    |**Profile Properties**|
    |Profile Name|Provide a unique name for this profile.|
    |Reuse Output|*\(Optional\)* If your profile is based on an existing profile, then select this option. Selecting this option ensures that AEM Guides does not extract the contents of DITA-OT package again and reuses the existing DITA-OT package.|
    |Profile Extract Path|*\(Optional\)* Specify the path where DITA-OT is kept on disk. By default, AEM Guides bundles a DITA-OT package in its repository and it is extracted on the disk at this path.<br>**Note** You can define this path using any existing system variable or property. See description the [DITA-OT Environment Variables](#id181NH0YN0AX) property for more information.|
    |Assigned Path|\(*Optional*\) Specify the path in your content repository for which this profile is applicable. You can specify multiple locations.|
    |**DITA-OT Properties**|
    |DITA-OT Timeout|\(*Optional*\) Specify the time \(in seconds\) for which AEM Guides waits for a response from the DITA-OT plug-in. If no response if received in the specified time, AEM Guides terminates the publishing task and the task is flagged as failed. Also, the failure logs are made available in the output generation log file. <br>Default value: 300 seconds \(5 minutes\)|
    |DITA-OT PDF Arguments|Specify the command-line arguments that are processed by the custom DITA-OT plug-in for generating the PDF output. For all custom DITA-OT profiles, specify the following command-line argument:`-lib plugins/org.dita.pdf2.fop/lib/`|
    |DITA-OT AEM Arguments|\(*Optional*\) Specify the custom command-line arguments that are processed by the custom DITA-OT plug-in for generating the AEM Site output.|
    |DITA-OT Library Paths|\(*Optional*\) Specify the additional library paths of DITA-OT plug-in.|
    |DITA-OT Build XML|\(*Optional*\) Specify the path of the custom Ant build script bundled with the customized DITA-OT plug-in. This path is relative to the DITA-OT directory on your file system.|
    |DITA-OT Ant Script Folder|\(Optional\) Specify the path of the DITA-OT Ant script folder. This path is relative to the DITA-OT directory on your file system.|
    |DITA-OT Environment Variables|*\(Optional\)* Specify environment variables to pass on to the DITA-OT process. By default, AEM Guides adds four variables - `ANT_OPTS`, `ANT_HOME`, `PATH`, and `CLASSPATH`. <br> You can reuse any of the existing system environment variables or properties for building new environment variables. For example, if you have `JAVA_HOME` system variable defined in your system and you want to define a new environment variable called `JAVA_BIN` that is built using `JAVA_HOME`. Then, you can add the definition of `JAVA_BIN` as:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Note** You can also use Java system properties to build environment variables. For example, if AEM start script defines a Java system property `java.io.tmpdir` to a temporary directory, you can use this property to define new variable as: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Important** To reuse any existing system variable or property, it must be enclosed within `${}`.|
    |Overwrite DITA-OT Output|*\(Optional\)* If this option is selected, then you can specify the DITA-OT package available on your local system to generate output using DITA-OT. This configuration is set on activation of the ConfigManager. <br> If you want to specify the path of a DITA-OT package that is stored on AEM server, then deselect this option.|
    |AEM DITA-OT Zip Path/ Local DITA-OT Directory Path|Depending on your selection in the Overwrite DITA-OT Output, specify the complete path where the custom DITA-OT.zip file is stored. This could be the path in your AEM repository or local system.|
    |DITA-OT Plug-in Path|Path of the custom plug-in. This plug-in is integrated automatically with the main DITA-OT package.|
    |Integrate Catalogs|\(*Optional*\) Path of the custom DTD and XSD catalog.xml files in the AEM repository. This should be provided only when the catalogs are missing from the DITA-OT package. These catalogs are automatically integrated with the main DITA-OT as a plug-in.|
    |Add System ID Catalog|\(*Optional*\) Select this option only if there are missing Public ID entries in the catalog or if the DITA files use only the System IDs that are relative to the server path from where they are uploaded.|
    |DITA-OT Temporary Path|*\(Optional\)* Specify a temporary location where DITA files are copied for processing. Before DITA-OT processes files, they are copied at this temporary location. By default, the temporary storage location is: <br> **Note** You can define this path using any existing system variable or property. See description the [DITA-OT Environment Variables](#id181NH0YN0AX) property for more information.|

    >[!NOTE]
    >
    >  The AEM Guides installer creates two environment variables that you can use to specify the path of the custom DITA-OT plug-in files. These environment variables are: DITAOT\_DIR, which contains the path of the DITA-OT directory on the file system; and DITAMAP\_DIR, which contains the path where the DITA map content is extracted on the file system.

1.  Click **Done** to save the profile.


>[!NOTE]
>
> You can export the custom DITA profile as a package and upload on the other AEM Guides instances to save time. For more information, see [appendix.md\#](appendix.md#).

## Integrate DITA specialization {#id211MB0E00XA}

DITA specialization is the process of creating new DITA structures by adding new elements or removing existing elements. To create a new DITA element, you can take an existing DITA element as the base and modify it as per your authoring requirements. In essence, DITA specialization allows you to create customized information models that meet your business requirements while retaining the benefits of the existing DITA architecture.

You can use the Profile feature to store custom DITA specialization settings. These settings can then be used at the time of authoring and publishing custom DITA content. AEM Guides allows you to use Public ID and System ID in your custom DTDs/XSDs.

>[!NOTE]
>
> AEM Guides Web Editor does not have support for XSDs.

Perform the following steps to create a new profile and configure it to use specialized DTDs and XSDs AEM Guides:

1.  Create a specialization folder on your local machine that contains the specialized DTDs and XSDs.

1.  Specify the DTD details in the `catalog.xml` file that must also be included in the specialization folder.

    >[!NOTE]
    >
    > In case of DITA 1.3, the default location for DTD `catalog.xml` file in the AEM repository is: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1.  Specify the XSD details in the `catalog.xml` file that must also be included in the specialization folder.

    >[!NOTE]
    >
    > In case of DITA 1.3, the default location for XSD catalog.xml file in the AEM repository is: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1.  Upload the folder to the following location:

    `/libs/fmdita/dita_resources`

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Click on the**DITA Profiles** tile.

    >[!NOTE]
    >
    > The Default Profile information is displayed on the Profiles page. If you have upgraded AEM Guides from version 2.2 to 2.5.1 or 2.6, then all changes made through the configuration manager are automatically picked and stored in the Default Profile.

1.  You can choose to edit the Default Profile, create a new profile, or duplicate settings from the Default Profile to create a new profile.

    >[!NOTE]
    >
    > You cannot delete the Default Profile. However, all new profiles that you create can be edited and deleted.

1.  In the **Schema** \> **Catalog** settings, specify the path of the custom DTD and XSD `catalog.xml` files in your AEM repository.

1. Select the **Add System ID Catalog** option.

    >[!NOTE]
    >
    > Select this option only if there are missing Public ID entries in the catalog or if the DITA files use only the System IDs that are relative to the local file path from where they are uploaded.

    For more information about other properties on the Profiles page, see the properties table in [Step 6](#id17A9F0D075Z) of the [Use custom DITA-OT plug-ins](#id181NH1020L7) section.

1. Click **Done** to save the profile.


>[!NOTE]
>
> You can export the custom DITA profile as a package and upload on the other AEM Guides instances to save time. For more information, see [appendix.md\#](appendix.md#).

