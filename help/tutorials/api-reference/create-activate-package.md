---
title: REST API for creating and activating packages
description: Learn about the REST API for creating and activating packages
exl-id: 5320727d-d6de-4ea7-b822-088f670687ab
---
# REST API for creating and activating packages {#id198CF0260Y4}

The following REST API allows you to create and activate CRX packages.

## Create and activate package 

A POST method that creates and activates CRX package.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/activate

**Parameters**:
The request query consists of the JSON rules string. The content type of the POST request must be set to `application/json; charset=UTF-8`.

**Example**:
The following examples shows the API call using the curl command:

    ```
    curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
    ```
