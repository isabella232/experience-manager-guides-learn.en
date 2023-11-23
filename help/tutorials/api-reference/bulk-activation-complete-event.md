---
title: Bulk activation complete event handler
description: Learn about bulk activation complete event handler
---
# Bulk activation complete event handler

Experience Manager Guides exposes `com/adobe/fmdita/replication/complete` event that is used to perform any operations after the completion of a bulk activation process. This event is triggered whenever a bulk activation process is completed. For example, if you run the bulk activation of an AEM site preset of a map, this event is called after the activation process ends.


You need to create an AEM event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:

```
com/adobe/fmdita/replication/complete 
```

**Parameters**:
|Name|Type|Description|
|----|----|-----------|
|`path`|String|The path of the file that triggered this event. <br> For example, `/content/output/sites/ditamap1-ditamap`. <br> It is a list of paths serialized as a JSON array.|
|`messageType`|String|The type of a message. <br>Possible option : `REPLICATION`|
|`action`|String|This is the action performed. <br>Possible option : `BulkReplicate`|
|`user`|String|The user who started the operation.|
|`result`|String|The result of the Bulk Activation. It is a serialized JSON Object: <br>`{"success":boolean,"code":integer,"message":"" }`|
|`agentId`|String|The agentId used in the replication. For example, `"publish"`.|
|`importMode`|String|Import mode used in Activation. The possible options are: <br>`REPLACE, MERGE, UPDATE`.|

