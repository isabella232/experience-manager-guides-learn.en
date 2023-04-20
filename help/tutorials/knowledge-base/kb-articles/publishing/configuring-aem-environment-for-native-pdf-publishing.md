---
title: Configuring AEM environment for Native PDF publishing
description: Configuring AEM environment for Native PDF publishing

---

# Configuring AEM environment for Native PDF publishing

AEM Guides includes a native PDF publishing engine that enables users to design, develop and publish the content in PDF format.

It provides the ability to create different page layouts, CSS templates and design the PDF templates in conjunction with the page layouts and CSS.

The steps for configuring this Native PDF in AEM Guides differ depending on the operating system. Use the configuration steps below based on the operating system on which AEM is installed.

## Prerequisites

Minimum requirements for setting up Native PDF:

- Installed Java Platform, Standard Edition 8 or 11 JDK (Java SE Development Kit) and JRE (Java SE Runtime Environment)
- AEM 6.5 SP13, SP12, SP11, or SP10
- Guides 4.1 and above versions (Non-UUID or UUID)

Native PDF publishing engine needs Oracle JDK to generate the node modules in the AEM crx-quickstart folder. It supports the following operating systems by default:

- Windows 10, windows 2019 server and above.
- Linux – (RHEL 8 and above, CentOS 7 and above, Ubuntu 18 and above versions)
- Mac OS (Intel-based)

## Configuration steps for Windows Server (JAVA 11/8)

1. Ensure that AEM server is down.
2. On the Windows taskbar, right-click the Windows icon and select System.
3. In the Settings window, under Related Settings, click Advanced system settings.
4. On the Advanced tab, click Environment Variables.
5. In system variables section, click "_New_" to create a new environment variable.
6. Enter variable name as JAVA_HOME.
7. In the value field, provide the Java Installation path and click Ok.

   For example:

   JAVA 11:

   C:\Program Files\JAVA\jdk-11.0.15.1

   JAVA 8:

   C:\Program Files\JAVA\ jdk1.8.0_144

8. Add select Path from system variables and click Edit.

9. Now, inside Path variables provide the value of Server path and click Ok.

   For example:

   JAVA 11:

   %JAVA_HOME%\bin\server\

   JAVA 8: 
   
   %JAVA_HOME%\jre\bin\server\

10. Click 'OK' again on Environment variables dialog.
11. Click 'OK' again on System Properties dialog.
12. Now, start the AEM server.
13. Generate native PDF from presets in web editor.

## Configuration steps for Linux Server (RHEL7/centOS 7)

1. Ensure that AEM server is down
2. Verify the JAVA_HOME variable by doing echo $JAVA_HOME
3. If JAVA_HOME variable is not set, then follow step 4. Otherwise, move to step 5 directly.
4. Set JAVA_HOME variable using the below commands based on the installed java version

   For example:

   JAVA 11:

    1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
    2. export PATH=$PATH: $JAVA\_HOME/bin
    3. export LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8:

    1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
    2. export PATH=$PATH: $JAVA\_HOME/bin

5. Restart AEM Server
6. Copy the "_node_modules.zip_" attached in the bottom of this article to the crx-quickstart/profiles/nodejs--b1aad0a7-9079-e56c-1ed8-6fcababe8166/ directory.
7. Open terminal in crx-quickstart/profiles/nodejs--b1aad0a7-9079-e56c-1ed8-6fcababe8166/ location.
8. Delete node_modules directory using below command

   **rm -rf node_modules**

9. Unzip node_modules.zip using below command

   **unzip node_modules.zip**

10. If unzip command is not installed/recognized, it can be installed using following command

    **yum install unzip**

11. Install fontconfig package.
    Command: yum install fontconfig
12. Generate native PDF from presets in web editor.

**NOTE** : node_modules.zip package can be downloaded [here](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

Manually importing the downloaded node modules for Linux operating system is a workaround for users who are on Guides 4.1 or earlier versions.

## Configuration steps for Mac machine (JAVA 11/8)

1. Install Oracle JAVA 11 or Oracle JAVA 8.
2. Set JAVA_HOME environment variable to the installed JAVA directory.
3. Open a Unix shell.
   (Bash is used here for setting up the configuration)

   Command: nano ~/.bashrc

4. Set JAVA_HOME variable using the below commands based on the installed java version

   For example:

   JAVA 11:

   export JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. Reload bashrc

   Command: source ~/.bashrc.

6. Verify JAVA_HOME is set using command echo $JAVA_HOME

7. Execute the below three commands from AEM installation path

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs--b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) find . -type d -exec chmod 0755 {} \;
   ii) find . -type f -exec chmod 0755 {} \;
   iii) ./node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js --prefix . install --unsafe-perm --scripts-prepend-node-path

8. Verify if Java is installed using the below command

   i) Run **./node-darwin/bin/node** command from /crx-quickstart/profiles/nodejs--b1aad0a7-9079-e56c-1ed8-6fcababe8166 folder

   ![mac](../assets/publishing/mac.png)

   ii) a = require('java')

9. Install fontconfig package.
   Command: apt install fontconfig

10. Generate native PDF from presets in web editor.

## Troubleshooting

Below are the common errors that may occur during PDF Generation when environment variables are not set properly.

### Null pointer Exception in Windows/Mac OS

![null pointer exception](../assets/publishing/null-pointer-exception.png)

### Missing Libraries in RHEL 7 Linux OS

![missing libraries](../assets/publishing/missing-libraries.png)

If you encounter any issues while performing any of the above steps, post your question on the AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) for assistance.
