---
title: Configuration overrides
description: Learn how to Configuration overrides
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
---
# Configuration overrides {#id216IFC003XA}

For making any configuration updates, the following generic approach should be used:

1.  Access your Cloud Manager's Git repository.

1.  Create a new JSON file at the following location:

    src/main/content/jcr\_root/apps/fmditaCustom/config/

1.  Name the file in the following format:

    $\{PID\}.cfg.json

    Here, the PID is the process ID of the configuration.

1.  Add properties in the JSON file using the following format:

    ```
    {
       "aem.adminuname": "updatedUserjson",
       "valid.characters": "[-a-zA-Z0-9_@$]",
       "dita.serialization": true
    }
    ```

1.  Commit the changes and run the Cloud Manager pipeline to deploy the updated configuration.


**Parent topic:**[Download and install](download-install.md)
