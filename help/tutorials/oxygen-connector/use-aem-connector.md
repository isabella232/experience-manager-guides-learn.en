---
title: Oxygen Plugin for Adobe Experience Manager Guides
description: Learn how to use Oxygen Plugin for Adobe Experience Manager Guides to create and manage your content.
---

# Oxygen Plugin for Adobe Experience Manager Guides {#id1645H6010Q5}

The Oxygen Plugin for Adobe Experience Manager Guides \(later referred to as Oxygen Plugin for AEM Guides in the guide\) enables you to connect the Oxygen XML Author with the Adobe Experience Manager \(AEM\) repository for authoring and managing content. You can use the plugin to browse, search and open files; check-out and check-in files; upload folders and files on AEM repository. The AEM Guides panel in the desktop application allows you to mark the desired folders \(from AEM repository\) to the favorite folders list for quick access. Additionally, you can install a package in AEM web interface and open your DITA files in Oxygen XML Author directly from the AEM web interface.

## Download and install {#id1826M0L0PUI}

The Oxygen Plugin for AEM Guides is made available through your Adobe Software Distribution Portal. Search for "oxygen" in the Experience Manager tab and then download the plugin installer from your [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).

>[!NOTE]
>
>Check for the Oxygen Connector version compatibility from the release notes for the specific Adobe Experience Manager Guides.

Once you have the installer, install it on your local machine where the Oxygen XML Author is installed. Before you begin the installation process, you must ensure that your system meets the technical requirements to install the Oxygen Plugin for AEM Guides.

### Technical requirements 

-   Oxygen XML Author version 24.1

-   Adobe Experience Manager Guides version 3.4 or higher

-   Adobe Experience Manager version 6.5 with Service Pack 10, 11, 12, and 13

-   Operating system supported by Oxygen XML Author version 24.1

-   Java Development Kit
    -   Oracle SE 8 JRE 1.8

### Install the plugin on Windows 

>[!IMPORTANT]
>
>If you have an older version of the plugin installed on your system, ensure that you uninstall it before starting the installation process. See the **Uninstalling Packages** section in the [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) article for uninstallation instructions.

Perform the following steps on the system where Oxygen XML Author is installed:

1.  Launch the installer's `.exe` file.

    The installation wizard's welcome screen appears.

1.  Click **Next** and browse to location where Oxygen XML Author's .exe file is available.

1.  Select the file, and click **Open**.

    The selected file's location is added in the installation wizard.

1.  Click **Next**.

1.  Click **Install**.

1.  Click **Finish** to close the installation wizard.
1.  Launch Oxygen XML Author.

    The AEM Guides panel is displayed in the Oxygen XML Author.

    ![](images/oxygen-aem-connector.png)

    >[!NOTE]
    >
    >If you do not see the AEM Guides panel, see the workarounds in the troubleshooting section—[Missing AEM Guides panel](#id192BH200ZAX).


### Install the plugin on Mac 

>[!IMPORTANT]
>
>If you have an older version of the plugin installed on your system, ensure that you uninstall it before starting the installation process. See the **Uninstalling Packages** section in the [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) article uninstallation instructions.

Perform the following steps on the system where Oxygen XML Author is installed:

1.  Locate the plugin's .dmg file on your system.

1.  Double-click the .dmg file to open the file content.

    The .dmg file contains an aem-connector-x.x folder and a aem-connector-x.x-setup file.

    >[!NOTE]
    >
    >x.x in the filenames is the version number of the plugin.

1.  Copy the aem-connector-x.x folder in the plugins folder of Oxygen XML Author.
1.  Double-click the aem-connector-x.x-setup file to launch the installer.

1.  Launch Oxygen XML Author.

    The AEM Guides panel is displayed in the Oxygen XML Author.

    ![](images/oxygen-aem-connector-mac.png)

    >[!NOTE]
    >
    >If you do not see the AEM Guides panel, see the workarounds in the troubleshooting section—[Missing AEM Guides panel](#id192BH200ZAX).


### Install the package for enabling document editing feature from AEM web interface {#id182CE0Q0TY4}

As an author, you can open and edit your DITA maps or topics in Oxygen XML Author directly from the AEM web interface. To enable this feature in AEM web interface, your AEM administrator needs to install a package in your AEM authoring instance.

As an AEM administrator, perform the following steps to install the package:

1.  Get the package's .zip file from your IT team.
1.  Log into your AEM instance *\(as an administrator\)* and navigate to the CRX Package Manager. The default URL to access the package manager is

    `http://<server name>:<port>/crx/packmgr/index.jsp`

    The Package Manager manages the packages on your local AEM installation. For more information about working with the Package Manager, see [How to Work With Packages](https://docs.adobe.com/docs/en/aem/6-3/administer/content/package-manager.html) in AEM documentation.

    ![](images/package-manager.png)

1.  To upload the Oxygen package, click **Upload Package**.
1.  In the Upload Package dialog, navigate to the Oxygen package file that you downloaded in Step 1 and click OK.

    The package is uploaded on to your AEM instance.

1.  To start the installation process, click **Install**.

    ![](images/oxygen-package.png)

1.  In the Install Package dialog, click **Install**.
1.  After installation completes, click the Home button in the upper-left corner of the CRX Package Manager.
1.  Select a DITA file in your assets folder.

    **Edit in Oxygen** option is available in the toolbar. For more information about using this option, see [Open DITA topic in Oxygen XML Author from AEM web interface](#id182CE0I905Z).

    >[!NOTE]
    >
    >The **Edit in Oxygen** option is visible when you select one DITA topic. If you select multiple topics, the option will not be visible.


## Configure the Oxygen Plugin for AEM Guides {#id1826KF00AHS}

After you have downloaded and installed the plugin, you need to configure the followings to work with the plugin:

-   **Web authentication settings**: Settings for SSO authentication in the plugin for AEM Guides.
-   **General Settings**: Connection settings for the plugin, such as AEM server URL, login details, and so on.
-   **Preference for profiling attribute customization**: This configuration is required for the profiling attribute schemes for the documentation sets.

### Web authentication settings 

JxBrowser is used for SSO Authentication by the Oxygen connector plugin. It is a chromium based browser. For java 9+ access to non public API's is required and the you must explicitly grant this access to JxBrowser. For more details, see [JxBrowser Troubleshooting](https://jxbrowser-support.teamdev.com/docs/guides/troubleshooting/issues.html).

Update the given files to configure the web authentication settings in the Oxygen Plugin for AEM Guides:

>[!NOTE]
>
>Take a backup of the file before updating it.

**For Mac and Oxygen 24.1**

Add the following lines in env.sh

```java
--illegal-access=permit\
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED\
--add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED\
--add-exports=java.desktop/sun.awt=ALL-UNNAMED\
--add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Add the following lines in the oxygenAuthor.sh

```java
-Djdk.module.illegalAccess=permit\-Djava.ipc.external=true\
```

**For Windows and Oxygen 24.1**

Add the following lines in env.bat

```java
--illegal-access=permit --add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED --add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED --add-exports=java.desktop/sun.awt=ALL-UNNAMED --add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Add the following lines in the oxygenAuthor.bat

```java
-Djdk.module.illegalAccess=permit -Djava.ipc.external=true
```

>[!NOTE]
>
>You need to run oxygen from oxygenAuthor.sh for Mac and oxygenAuthor.bat for Windows as an administrator.

### General settings 

Perform the following steps to configure the connection settings in the Oxygen Plugin for Adobe Experience Manager Guides:

1.  In the AEM Guides panel, click the settings icon and then select **Settings**.

    ![](images/settings.png)

1.  Specify the following details:
    -   **Server URL**: URL of the AEM server, for example:

        ```http
        http[s]://<host>:<port>
        ```

        In the above URL, specify the host name and port of the server where AEM server is deployed.

        >[!IMPORTANT]
        >
        >If your AEM server is deployed on port 80 or 443, then you do not need to specify it in the URL.

    -   **Authentication:** Choose from **Basic \(Username/Password\)** or **Web Authentication**. In case you select **Basic** authentication you need to enter the **Username** and **Password** in the Preferences dialog.

        If you select Web Authentication, then you are shown the AEM Login screen. Enter your login credentials and click the **Sign In** button. On successful login, the AEM Login screen closes and the AEM Guides panel displays the files list from the AEM server.

    -   **Connection Timeout**: Specify time in seconds that the client will wait for a response from the AEM server. In case no response from the server is received within the specified time, the request is terminated. The default value is 20 seconds.

    -   **Local Folder**: Location on your local machine where the files from AEM repository are stored after checkout. If you specify a location that does not exist on the drive, then the plugin creates that location.
    -   **Open File when Checked out**: If selected, opens the files on checkout.
    -   **Close File when Checked in**: If selected, closes the files on check-in. Before closing the file, you are shown a pop-up wherein you can specify the version comments.
    -   **Show Checkin Dialog on Closing File**: If selected, you are shown a pop-up on closing a file. From the pop-up, you can choose to check in the file or close the file without checking in.
    -   **Auto-Checkout File when Opened**: If selected, double-clicking on a file automatically checks it out and opens it for editing. In case the file is already checked-out, then it is simply opened up for editing. If this option is not selected, then opening a file on which you don't have a lock opens it up in read-only mode.
1.  Click **OK**.

### Preference for profiling attribute customization {#id1827K0D0OHT}

You need to configure the preferences in Oxygen XML Author to use the profiling attribute associated with the DITA topics in the AEM repository.

Perform the following steps to configure profiling attributes:

1.  In Oxygen XML Author, click **Options** \> **Preferences**.
1.  In the **Document Type Association** tab, select **DITA**, and then click **Extend**.

    ![](images/document_type_association.png)

1.  In the **Classpath** tab, select com.adobe.o2.connector in the **Use Parent Class Loader From Plugin with ID** drop-down.

    ![](images/dita-extension.png)

1.  In the **Extensions** tab, make the following changes:
1.  -   Click **Choose** next to the **Author Extension State Listener** under **Individual Extensions** and select CustomAuthorExtensionStateListener - com.adobe.o2.framework.extn in the **Class** list. Click **OK**.
-   Click **Choose** next to the **Author Custom Attribute Value Editor** under **Individual Extensions** and select CustomValueEditor - com.adobe.o2.framework.extn in the **Class** list. Click **OK**.
    The following screenshot shows the configured **Extension** tab for DITA topics:

    ![](images/dita-topic-extension-tab.png)

1.  Click **OK** on all dialog boxes to save your changes.

### Configure DITA map extension 

The DITA map extension configuration is required to enable opening of map files in Oxygen XML Author directly from the AEM web interface. These configurations are similar to the configurations for profiling attributes done in the preceding procedure.

Perform the following steps to configure the DITA map extension:

1.  In Oxygen XML Author, click**Options** \> **Preferences**.
1.  In the **Document Type Association** tab, select **DITA Map**, and then click **Extend**.
1.  In the **Classpath** tab, select com.adobe.o2.connector in the **Use Parent Class Loader From Plugin with ID** drop-down.
1.  In the **Extensions** tab, make the following changes:
1.  -   Click **Choose** next to the **Author Extension State Listener** under **Individual Extensions** and select CustomDITAMapAuthorExtensionStateListener - com.adobe.o2.framework.extn in the **Class** list. Click **OK**.
-   Click **Choose** next to the **Author Custom Attribute Value Editor** under **Individual Extensions** and select CustomValueEditor - com.adobe.o2.framework.extn in the **Class** list. Click **OK**.
-   *\(Optional\)* If you do not want to resolve references while opening a map file, then you need to perform the following additional configuration:

    Click **Choose** next to the **References Resolver**under **Individual Extensions** and select CustomDITAMapReferenceResolver - com.adobe.o2.framework.extn in the **Class** list. Click **OK**.

    The following screenshot shows the configured **Extension** tab:

    ![](images/dita-map-extension-tab.png)

1.  Click **OK** on all dialog boxes to save your changes.

## Work with Oxygen Plugin for AEM Guides {#id1826JG00WY4}

### AEM Guides panel 

The following screen shows the AEM Guides panel.

![](images/connector-panel.png)

**A**\) Shows the Search bar.

**B**\) Shows the Favorites folder. By default, it is empty. You can add folders from the AEM repository as favorite, the favorite folders are then shown here.

**C**\) The DAM folder shows the AEM repository. You can expand and collapse the folder view.

**D**\) The Settings \(gear\) icon with following options:

-   **Connect**: Select this option to connect to the AEM server. The option is disabled when Oxygen XML Author is connected to the AEM Server.
-   **Refresh**: Select this option to get the latest status of the files and folder from the AEM repository.

    >[!NOTE]
    >
    >Ensure that you save your files before you refresh them. When you select **Refresh** option, you get a warning to save your files before refreshing them. If you haven't saved your files, you can click **Cancel** and save them.

-   **Settings**: You can use this option to open the general Preferences dialog of the Plugin.
-   **Logout**: Select this option to close the AEM server connection. This option is available only if you are using the Web Authentication mode.

### Context menu Functions 

The functions of the Oxygen Plugin for AEM Guides are available on right-clicking a folder or file in the AEM repository. The functions available for the folders are different from the files. Here is a complete list of functions in Oxygen Plugin for AEM Guides context menu:

-   **Open**: Opens the selected file or expands the selected folder.
-   **Open In**: You can choose to open the selected file in AEM Guides' Web Editor or Map Dashboard, or Map Editor. For more information about these options, see [Open file in AEM Guides' editor](#id195GH0V30KX).
-   **Check-out**: Checks out a file from AEM repository. For more details, see [Check-out files](#id195HC020TS4).
-   **Check-out with dependents**: Checks out a file with its direct references. For more details, see [Check-out files](#id195HC020TS4).
-   **Check-out with read-only dependents**: Checks out the selected file along with its dependents. You cannot make any changes in the dependent files. For more details, see [Check-out files](#id195HC020TS4).
-   **Cancel check-out**: Cancels the checked-out file, closes the file from the editor, and reverts the changes to the last version of the file saved on the server.
-   **Refresh**: In case of a file, fetches the latest copy of the file from the AEM repository. For a folder, it fetches the folder structure and file's status. This means that is a file is added, then it will be shown in the AEM Guides View. Also, if a file is checked out on AEM server, doing a Refresh in Oxygen Author will show the file as checked out. However, this does not update the files list in the *Files Checked-Out in AEM Guides* View.
-   **Refresh Checked-out Files**: Refreshes the list of checked out files in the *Files Checked-Out in AEM Guides* View. If a file is checked out on AEM server, then doing a Refresh will update the list of checked out files in the *Files Checked-Out in AEM Guides* View. However, if a new file has been added or the status of a file has changed, then it does not update it in the AEM Guides tree view. To update the status of files on AEM, you must do a Refresh.
-   **Check-in**: Checks in a files that you have checked out. For more details, see [Check in a file](#id182CF0J0FHS).
-   **Check-in with dependents**: If you have checked out files with dependents, then this option checks in the main file along with its dependents. For more details, see [Check in a file](#id182CF0J0FHS).
-   **Create Folder**: Creates a folder in the AEM repository. This option is available only at a folder-level.
-   **Upload File\(s\)**: Uploads single or multiple files. For more details, see [Upload files and folders](#id195HC03F03J).
-   **Upload with dependents**: Uploads DITA files \(XML, DITA, Book map, or DITA map\) with its dependents. For more details, see [Upload files and folders](#id195HC03F03J).
-   **Upload Folder**: Uploads a folder on the AEM repository. For more details, see [Upload files and folders](#id195HC03F03J).
-   **Add to Favorites**: Adds a folder to the *Favorites* folder in the AEM Guides panel. It is recommended to add your working folder here, which makes it easier to sync files and file's status from AEM.
-   **Remove from Favorites**: Removes a folder from *Favorites*. For more details, see [Add or remove Favorites](#id195HC04405P).
-   **View Metadata**: Shows the metadata such as DITA Class, document's Title, Type, UUID, and other information associated with a file. For more details, see [View a file's metadata](#id195GHN0H05C).
-   **View Versions**: Shows the version history of a file. For more details, see [View a file's version history](#id195GI000D5Q).

### Open a file in Oxygen XML Author {#id195GHJ0A0UB}

Once you have connected to the AEM repository, you can open files for editing in the Oxygen XML Author. Perform the following steps to open a file for editing in the Oxygen XML Author:

1.  Right-click on a file in the AEM Guides panel that you want to open for editing.

1.  Select **Open** from the context menu.

    The file is opened in Oxygen XML Author's editor.

    ![](images/guid-in-file-tab.png)

    When you hover the mouse pointer over a file's tab, you are shown the server path along with its UUID. In the above screenshot, the UUID of the document is highlighted.


If you have selected the **Auto-Checkout File when Opened** option \(in the Preferences dialog\), then on opening a file, the file is automatically checked out and is available for editing. To open a file, you can either double-click on a file name or right-click on the file name and choose **Open** from the context menu. If this option is not selected, then the file is opened in read-only mode.

>[!NOTE]
>
>You can also double-click on a file to open it.

### Open file in AEM Guides' editor {#id195GH0V30KX}

If you want to use the editors available in AEM Guides, you can do so by selecting the required option from the context menu. Perform the following steps to use AEM Guides' editor in place of Oxygen XML Author's editor:

1.  Right-click on a file in the AEM Guides panel that you want to open for editing.

1.  Select **Open In** from the context menu and choose from the following options:

    - **Web Topic Editor**: If the file you are opening is a .xml or .dita file, then you can open it for editing in the Web Editor. Choose the **Web Topic Editor** option to open the selected file for editing in the Web Editor.

    - **Map Dashboard**: You can choose to edit a .ditamap file in the map dashboard wherein you can perform various operations on the map file. These operations depend on the role/group that you belong to.

    - **Web DITA Map Editor**: If you want to open the .ditamap file for editing in the Map Editor, then choose this option. Using the DITA Map Editor option, you can add or remove topics, add relationship tables, and perform other operations on your map.


### Check-out files {#id195HC020TS4}

When you checkout a file, it is stored locally on your system and locked for editing in the AEM repository. Perform the following steps to check-out a file:

1. Right-click a file in the AEM Guides panel.
1. Select one of the following options:
   -  **Check-out:** Checks out a file from AEM repository and makes it available for editing.
   -  **Check-out with dependents**: Checks out a file with its direct references. You can make changes in parent and child pages using this option. Oxygen Plugin for AEM Guides supports checking out one level of dependents. For example, Map A references Topic A and Topic A references Topic B. Checking out Map A will checkout Topic A regardless of its level in the TOC hierarchy. However, it will not check out Topic B because it is not directly linked from Map A.
   -  **Check-out with read-only dependents**: Checks out a file and downloads its dependents to your local machine as read-only copies. You cannot make any changes in the dependent files.

If you have selected the **Open Files on Checkout** option \(in the Preferences dialog\), then on checking out a file, the file is automatically opened for editing.

If you have selected the **Auto-Checkout File when Opened** option \(in the Preferences dialog\), then on opening the file, the file is automatically checked out and is made available for editing. To open a file, you can either double-click on a file name or right-click on the file name and choose **Open** from the context menu.

When a file is checked-out, the icon of the file changes to show its locked status.

![](images/check-out-file.png)

In the above screenshot, a file checked out by other user is shown with a black colored lock icon \(A\). File checked out by the current user is shown with a green colored lock \(B\).

>[!NOTE]
>
>If the checked-out file is deleted or moved to any other folder in AEM, you get an error message when you check-in the file. Make sure that the checked-out file is not moved or deleted using the AEM web interface.

### Check in a file {#id182CF0J0FHS}

When you check in a file, the local copy from your system is stored in the AEM repository, and the lock on the file is removed. Perform the following steps to check in a file:

1. Save your file by clicking **File** \> **Save**.

1. Right-click on a checked-out file and choose from the following two options:

   -  **Check-In**: Checks-in the selected file from your local system into AEM repository.
   -  **Check-In with Dependents:** If you have checked-out a file along with its dependents, then use this option to check in all dependent files in one single operation. On selecting this option, you are shown the Check-In dialog with all dependent files. Click OK to check-in all files at once.

     If you have not checked out dependent files and then you choose this option, then only those dependent files that you have \(separately\) checked out will be checked in. You will be shown a list of files that could not be checked in:

     ![](images/check-in-error.png)

     It is strongly recommended not to move a file that is checked out. However, if a checked out file is moved to a different location, then you must cancel the checkout on that file. If you want to make updates on that file, then check out the file again, make changes, and then check it back in. If you try to check in a file that has been moved from its original location, then you will get an error.

     If a dependent file is checked out in AEM, then Check-In with Dependents will not show the dependent file in the Check-In dialog. To get a list of dependent files that are checked out in AEM, you must do a folder Refresh.

     Similarly, if you have checked-in a dependent file through AEM, the file list is not refreshed in Oxygen Author until you do a folder Refresh and Refresh Checked-Out Files. If you do a Check-in with Dependents with some files checked in through AEM, then you will get an error listing the files that could not be checked in.

1. \(Optional\) In the Check-In dialog, add a comment in **Version Comments** text box.

   >[!NOTE]
   >
   >This comment is displayed in the AEM version history of the file.

1. Click **OK**.

>[!NOTE]
>
>If the checked-out file is deleted or moved to any other folder in AEM, you get an error message when you check-in the file. Make sure that the checked-out file is not moved or deleted using the AEM web interface.

### Files Checked-Out in AEM Guides View 

When you have in multiple folders, then it is not easy to find out how many files are checked out in one view. AEM Guides provides Files Checked-Out in AEM Guides View that gives one complete snapshot of currently checked-out files. Using this view, you can easily find out which files have been checked by you in AEM repository using AEM Guides. Perform the following steps to access and work with this view:

1. Click **Window** \> **Show View** \> **Files Checked-Out in AEM Guides**.

    The Files Checked-Out in AEM Guides view is displayed.

    ![](images/files-checkedout-view.png)

1.  Right-click on a file in this view to get the following options:

    -   [Open](#id195GH0V30KX)
    -   [Open In](#id195GH0V30KX)
    -   Cancel Check-Out
    -   [Check-In](#id182CF0J0FHS)
    -   [Check-In with Dependents](#id182CF0J0FHS)
    -   [View Metadata](#id195GHN0H05C)
    -   [View Versions](#id195GI000D5Q)

**Notes on Files Checked-Out in AEM Guides View:**

-   The *Files Checked-Out in AEM Guides* View maintains user's sessions. This means that files checked out by the current user are stored and maintained in the view across the same user's sessions \(or cache\).

-   If the user changes the login credentials or the AEM server, then the checked-out file's data \(or cache\) in the view is reset. The user must manually run a *Refresh Checked-Out Files* command on each folder from where the files were earlier checked out. To simplify this, it is recommended to add your working folders to *Favorites* from where you can quickly do a folder refresh.

-   You can sort the files list on the basis of their File names, Title, or Path. If a new file is checked out, the file appears in sorted order in the view.


### Upload files and folders {#id195HC03F03J}

Perform the following steps to upload files or folders:

1.  Right-click a folder in the AEM Guides panel.
1.  Select one of the following options:
    -   **Upload File\(s\)**: Select this option to upload single or multiple files to the selected folder in the AEM repository. In the Select files \(s\) to upload dialog, select the files and click **Open**.
    -   **Upload with dependents**: Select this option to upload a DITA file with its dependents. In the Select file to upload dialog, select the files and click **Open**.
    -   **Upload Folder**: Select this option to upload a folder in the AEM repository. In the Choose dialog, select the folder and click **Choose**.

**Additional notes on working with UUID-based files**:

The following points must be considered while moving or copying content from your local system to AEM repository:

-   When uploading one or more files, a new UUID is generated for files not having any UUID. This UUID is added in the `topic id` of a DITA file.

-   When copying a folder, the references to the files \(within the folder\) are automatically updated in all DITA maps referencing files in that folder.

-   When copying a DITA map file, the UUID references within the map file are not changed.

-   If a file or a folder has a conflict or has a duplicate, then a unique filename is generated for the new file being copied or moved.

-   No two files can have the same UUID. A unique UUID is assigned to all new files.

-   If in case a file is being uploaded by two different users at the same time, then the file that is processed later overwrites the earlier file. However, such a practice should be avoided.

-   When you checkout content from AEM repository and make changes on your local system, ensure that file name is not changed at the time of uploading the file.


### Add or remove Favorites {#id195HC04405P}

Perform the following steps to add or remove a folder to the Favorites folder in the AEM Guides panel:

-   Right-click a folder and select **Add to Favorites**. You can add a folder to favorites if it is not in Favorites.
-   You can remove a folder from favorites in following ways:
    -   Right-click a folder in the **Favorites** folder and select **Remove from Favorites**.
    -   Right-click a folder in the AEM repository under **DAM** folder that is already added as favorite and select **Remove from Favorites**.

### View a file's version history {#id195GI000D5Q}

Perform the following steps to view a file's version history:

1.  Right-click on a file in the AEM Guides panel.

1.  Select **View Versions** from the context menu.

    File's version history is displayed in the Versions dialog.

    ![](images/version-history.png)


### View a file's metadata {#id195GHN0H05C}

Perform the following steps to view a file's metadata:

1.  Right-click on a file in the AEM Guides panel.

1.  Select **View Metadata** from the context menu.

    File's metadata such as the DITA Class, Document State, modification date, size, Title, and UUID are displayed in the Metadata dialog.

    ![](images/metadata.png)


## Search a topic in the AEM repository {#id1826J20405Z}

You can search for topics in the AEM repository using the Search bar in the AEM Guides panel. You can search in the entire DAM folder or select a folder and then search for a topic in that folder. The search result shows the topics that have text matching with your search query.

Perform the following steps to search topics:

1.  Select a folder in the AEM repository where you want to search a topic.
1.  Enter the search query \(for example, `introduction`\) in the Search bar of the Oxygen Plugin for AEM Guides.
1.  Click the search button or press Enter.

    The result is displayed in the Search Results tab as a list with the file path. If there is no matching result for your search query, No results found in <path of the selected folder\> message is displayed.

    ![](images/search.png)

1.  \(Optional\) Double-click a file in the search result to open it in Oxygen XML Author.
1.  To go back to the AEM Repository view, do one of the following:
    -   To view the AEM Repository view without clearing the search results, click **Browse** tab.
    -   To clear the search results and view the AEM Repository, Click Delete search icon.

## Open DITA topic in Oxygen XML Author from AEM web interface {#id182CE0I905Z}

You can open and edit your DITA topic in Oxygen XML Author from the AEM web interface. You need to install a package in AEM to enable this option. For more information about package installation, see [Install the package for enabling document editing feature from AEM web interface](#id182CE0Q0TY4).

>[!NOTE]
>
>The **Edit in Oxygen** option is accessible from various places in AEM: when a topic is selected, when a topic is previewed, or from Topics and Reports tab of DITA map console. If you select multiple topics, then the option is not visible in the toolbar.

**Open a DITA topic**

Perform the following steps to open a DITA topic in Oxygen XML Author:

1.  Select a topic in your assets and click **Edit in Oxygen** option in the toolbar.

    >[!NOTE]
    >
    >If the topic is not checked out, then it is first checked out and then opened in Oxygen in the edit mode.

1.  Select Oxygen XML Author *<version\>* in the **Launch Application** message box. You can select **Remember my choice for AEM links** option to save your preference.

**Edit a DITA topic**

Perform the following steps to edit a DITA topic in Oxygen XML Author:

1.  Select and check-out a topic in your assets.
1.  Click **Edit in Oxygen** option in the toolbar.

    >[!NOTE]
    >
    >If the topic is not checked out, then it is first checked out and then opened in Oxygen in the edit mode.

1.  Select Oxygen XML Author *<version\>* in the **Launch Application** message box. You can select **Remember my choice for AEM links** option to save your preference.
1.  Edit the topic in Oxygen XML Author.
1.  Check-in the topic from the Oxygen Plugin for AEM Guides.

    For more information about checking-in a topic using Oxygen Plugin for AEM Guides, see [Check in a file](#id182CF0J0FHS).

    >[!NOTE]
    >
    >Make sure that you check-in the topic using Oxygen Plugin for AEM Guides, if you check-in from the AEM web interface, the changes you make in Oxygen XML Author are not saved in the checked-in version of the topic.


## Work with attribute profiles {#id1827JA002YK}

AEM Guides allows you to easily create and associate conditional attributes using the relevant DITA attributes. You can define conditional attributes at the global level or folder level. The globally defined conditions are visible across all projects and folder level conditions are visible only in projects created within the specified folder. Content authors can use these conditional attributes to conditionalize content in their DITA topics or maps that they create or use. To know more about how to create conditional attributes in AEM using the AEM Guides, see *Configure conditional attributes for global or folder-level profiles* section in Install and configure Adobe Experience Manager Guides.

>[!NOTE]
>
>Make sure that you have added the conditional attributes in AEM and have set [Preference for profiling attribute customization](#id1827K0D0OHT) before you add conditional attributes to your content.

Perform the following steps to add conditional attributes to your content in Oxygen XML Author:

1.  Check-out and open a topic from the *Oxygen Plugin for AEM Guides*.
1.  Select the part of the content where you want to apply the conditional attributes.
1.  Double-click the conditional attribute in the Attributes panel of the Oxygen XML Author.

    ![](images/attribute-panel.png)

1.  In the **Available** column of the Edit Attribute dialog, select the attribute\(s\) and click **Add**.

    The following screen shows `audience` attributes.

    ![](images/edit-attributes.png)

1.  Click **OK**.

    The attributes are added to the content.


## Troubleshooting common issues {#id188ABC00RY4}

This topic covers some of the most common issues that you might face while working with the Plugin, along with their solutions.

### Missing AEM Guides panel {#id192BH200ZAX}

Issue
:   If you do not see the AEM Guides panel in Oxygen XML Author, try the following solutions:

Solution 1:
:   1.  In Oxygen XML Author, enable the plugin.

    Click **Options** \> **Preferences** \> **Plugins** and select **Oxygen Plugin for Adobe Experience Manager Guides.**

1.  Relaunch Oxygen XML Author.


Solution 2:
:   If you still do not see the AEM Guides panel, enable AEM Guides window.

    In Oxygen XML Author, Click **Window** \> **Show View** \> **AEM Guides**.

Solution 3:
:   Uninstall and reinstall the Oxygen Plugin for Adobe Experience Manager Guides.

    -   On Windows, uninstall the plugin from **Add or remove Programs** list. Then, reinstall the plugin.

    -   On Mac, access the aem-connector-x.x folder in the plugins folder of Oxygen XML Author, and move it to **Trash**. Then, empty the **Trash** folder.


### Configure port for DITA-OT transformation 

Issue
:   When you run any DITA-OT transformation on files that are processed by the Plugin, the transformation fails with the following error:

Solution
:   This issue has been fixed by adding a proxy server in-between DITA-OT and the Plugin. This proxy server processes and shares all files requested by DITA-OT for transformations. The default port on which this server has been configured is: `5972`. If you are using this port for some other server, then you can specify a different port for the proxy server.

    Perform the following steps to change the default port of the proxy server:

    1.  Browse to your \(user's\) home directory.

    2.  Create a file named aem\_connector\_proxy.

    3.  Open the file in any text editor and add an available port number in the first line of the file.

    4.  Save and close the file.

    5.  Restart Oxygen XML Author and run the DITA-OT transformation.


### AEM Guides panel does not browse to the opened file location 

Issue: When you choose to open a file for editing in Oxygen XML Author from AEM server, the file is opened for editing in Oxygen XML Author. However, AEM Guides panel does not show the location of the file in the navigation tree.

Solution: This issue has been observed in scenarios wherein the file path contains /content/dam twice in it. By default, all assets in AEM are stored under the /content/dam folder. If you upload or create a folder structure that also contains /content/dam in it, then this issue is observed. You can perform all normal operations on such files, however their location within the navigation tree is not shown by default. To access such file in the navigation tree, you have to manually browse to the file's location. Note that in the navigation tree the duplicate /content/dam path is replaced with /content/assets.

### Configure logging 

Issue: By default, the Oxygen Plugin for AEM Guides does not generate any logs, which makes it difficult to debug any error scenario.

Solution: Perform the following steps to enable logs generation feature in the Plugin:

    1.  Browse to the Oxygen XML Author's install location.

    1.  Open the oxygenAuthor19.1.vmoptions file in a text editor.

        >[!NOTE]
        >
        >The file's version number might differ based on the version number of the application installed on your system.

    1.  Append the following line in the file:

        ```java
        -Djava.util.logging.config.file=./log.properties
        ```

    1.  Save and close the file.

    1.  In the same location, create a file named log.properties with the following content:

        ```java
        handlers=java.util.logging.FileHandler
        java.util.logging.FileHandler.level = DEBUG
        java.util.logging.FileHandler.limit = 1048576
        java.util.logging.FileHandler.count = 5
        java.util.logging.FileHandler.pattern = %h/aem-plugin%g.log
        java.util.logging.FileHandler.formatter = java.util.logging.SimpleFormatter
        java.util.logging.FileHandler.format=[%1$tF %1$tT] [%4$s] %5$s %n
        ```

    1.  Save and close the file.

    1.  Start Oxygen XML Author.


    The plugin now creates logs in the user's home directory with the file name aem-pluginX.log \(*where X denotes the rotation number*\).

