---
title: REST API to register a data source connector
description: Learn about the REST API to register a data source connector
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
---
# REST API to register a data source connector {#id236LG0Y0CXA}

The following REST API allows you to register a data source connector.

## Register a data source connector 

A GET method that registers a data source connector.

**Request URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**:
|Name|Type|Required|Description|
|----|----|--------|-----------|
|`path`|String|Yes|A string which points to a path in the AEM repository. It can be a path in the `/content/dam or /var/dxml`.|

**Example**:   
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
