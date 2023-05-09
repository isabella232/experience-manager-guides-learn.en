# Configure Dispatcher {#id213BCM0M05U}

If you plan to use a Dispatcher on AEM Author instance along with AEM Guides, then you need to perform the following additional configurations to complete the setup:

>[!NOTE]
>
> Dispatcher is Adobe Experience Manager's caching and/or load balancing tool. For more details about using Dispatcher, see [Dispatcher Overview](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/dispatcher.html).

## Enable AllowEncodedSlashes in URLs 

URLs with encoded slashes are not enabled by default in AEM dispatcher setup, but while working in AEM Guides you need to enable this. To do this, you need to set the AllowEncodedSlashes parameter to On in Apache configuration as shown in the following snippet:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configure mime.types file for DITA 

When using a Dispatcher with AEM Guides, you must ensure that the DITA map and topic files are rendered as HTML for authors to view the content as they expect \(instead of raw text format\).

Perform the following steps to update the mime.types file:

1.  Connect to the Dispatcher server using SSH and browse to the httpd.conf file.

1.  Check the path of the " mime.types" file.

1.  Open the mime.types file and search for " text/html". The default mapping for " text/html" is:

    `text/html html htm`

1.  Update the mapping by adding ditamap and dita extensions as:

    `text/html html htm ditamap dita`

1.  Save and close the file.


This configuration update ensures that DITA map and topic files rendered by the Dispatcher are shown as HTML in the Assets UI.

## Allow User Preferences request URL 

When using a Dispatcher with AEM Guides, if your Author instance has a dispatcher in front, then make the following two changes:

-   Whitelist the POST request URL. A sample " `/filters`" rule is given below - Add this rule to dispatcher configurations file:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

-   Ensure the URL pattern " /libs/cq/security/userinfo.json" is not cached on Author dispatcher, so add a rule \(like below\) in author\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Parent topic:**[Download and install](download-install.md)

