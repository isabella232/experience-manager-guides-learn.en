# Verify AEM Guides installation {#id213BD030FBE}

Once you have installed AEM Guides, you need to verify whether the installation was successful or not. Perform the following steps to verify the installation process:

1.  Log into your AEM instance and navigate to the AEM Web Console Bundles page. The default URL to access the bundles page is:

    ```http
    http://<server name>:<port>/system/console/bundles
    ```

    A list of bundles is shown.

1.  Filter the list of bundles by entering fmdita in the filtering text box and press **Enter**.

    The list of bundles is filtered to show the bundles installed by AEM Guides. If the installation was successful, then all installed bundles will have a **Status** of **Active**.

    If any of the bundles does not have an **Active** status, then check the AEM logs to troubleshoot the installation issue.


>[!IMPORTANT]
>
> There are a number of performance optimization recommendations that you can consider to improve your system performance. See [Recommendations for performance optimization](download-install-recommend-perf-optimiz.md#) for details.

**Parent topic:**[Download and install](download-install.md)

