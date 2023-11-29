---
title: Basic troubleshooting
description: Resolve issues with basic troubleshooting in AEM Guides. Learn to view, copy, and check the log file in a text editor and resolve JSP compilation errors.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
---
# Basic troubleshooting {#id1821I0Y0G0A}

While working with AEM Guides, you could encounter errors while publishing or opening your document. Such errors could be in the DITA map, topic, or in AEM Guides process itself. This section provides information about how to access and parse information in the output generation log file. Also, if your DITA topic is too large, then you might see the JSP compilation error. This section also provides information about how to resolve the JSP compilation error.

## View and check the log file {#id1822G0P0CHS}

Perform the following steps to view and check the output generation log file:

1.  Once you have initiated the output generation process, click **Outputs** in the DITA map console.

    The **General** column of the **Generated Outputs** shows the icons to give a visual cue about the success or failure of the output generation.

    ![](images/output-general-settings.png){width="300" align="left"}

    In the above screenshot, the first and third icons show failed output generation. The second icon shows a successful output generation but with messages. The last one is a successful output generation without any message.

1.  Click on the link in the **Generated At** column after the job is complete.

    The log file opens in a new tab.

    ![](images/log-file.png){width="800" align="left"}

1.  Apply following filters to highlight the text in the log file:
    -   Fatal: Highlights the fatal errors in the log file with pink color.
    -   Error: Highlights the errors in the log file with orange color.
    -   Warning: Highlights the warnings in the log file with purple color.
    -   Info: Highlights the information messages in the log file with blue color.
    -   Exception: Highlights the exceptions in the log file with yellow color.
1.  Use the up and down navigation buttons to jump to the highlighted text in the log file.

    Alternatively, scroll through the log file and check the messages.


## Copy and check the log file in a text editor 

Perform the following steps to copy and check the output generation log file in a text editor:

1.  Once you have initiated the output generation process, click **Outputs** in the DITA map console.

1.  Click on the link in the **Generated At** column after the job is complete.

    The log file opens in a new tab.

1.  Click **Copy Log** button. The log file is copied to the clipboard.
1.  Open a text editor and paste the log file in the editor.

1.  Scroll through the log file and check for messages.

    The following information will help you determine whether there is an error in the DITA file or AEM Guides process:

    -   *DITA map file related error*: In case there is an error found in the DITA map file or any other file contained in the DITA map, the log file will contain a string, "BUILD FAILED". You can check the information given in the log file to locate the erroneous file and fix the issue.

    In the following sample log file snippet, you can see the `BUILD FAILED` message along with the reason for the error.

    ![](images/dita-error-in-log-file.png){width="650" align="left"}

    -   *AEM Guides-related error*: The other type of error that you can identify in the log file is related to AEM Guides process itself. In this case, the DITA map file is parsed successfully, but the output generation process fails because of some internal error in AEM Guides. For such kind of errors, you have to seek help from the technical support team.

    In the following sample log file snippet, you can see the `BUILD SUCCESSFUL` message, followed by other technical error.

    ![](images/process-error-in-log-file.png){width="650" align="left"}


## Resolve JSP compilation error 

If your DITA topic is too large, then you might see the JSP compilation error \(`org.apache.sling.api.request.TooManyCallsException`\) in your browser. This error might appear when you open a topic for editing, reviewing, or publishing.

Perform the following steps to resolve this issue:

1.  From the Global Navigation, select Tools and choose Operations \> Web Console.

    The Adobe Experience Manager Web Console Configuration page appears.

1.  Search for and click on the *Apache Sling Main Servlet* component.

    The configurable options for the Apache Sling Main Servlet are displayed.

1.  Increase the value for the *Number of Calls per Request* parameter as per your requirements.


**Parent topic:**[Output generation](generate-output.md)
