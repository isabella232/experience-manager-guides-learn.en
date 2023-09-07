# Post-processing event handler {#id175UB30E05Z}

AEM Guides exposes com/adobe/fmdita/postprocess/complete event that is used to perform any post-processing operations. This event is triggered whenever an operation is performed on a DITA file. The following operations on a DITA file trigger this event:

>[!NOTE]
>
> This event is not triggered for the Deletion operation in AEM 6.1.

- Upload
- Creation
- Modification
- Deletion

You need to create an AEM event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:
```
com/adobe/fmdita/postprocess/complete 
```

**Parameters**:
:   |Name|Type|Description|
|----|----|-----------|
|`path`|String|The path of the file that triggered this event. Typically, this is the file on which an operation has been performed.|
|``status``|String|The return status for the operation performed. The possible options are: -   SUCCESS: The post-processing operation completed successfully. <br>-   COMPLETED WITH ERRORS: The post-processing operation completed, but with some errors. <br>-   FAILED: The post-processing operation failed due to some fatal error.|
|`message`|String|In case the status is COMPLETED WITH ERRORS or FAILED, this parameter contains the details about the error or the reason of failure.|
|`operation`|String|The post-processing operation performed on the file. The possible options are:<br>-   Addition <br>-   Updation <br>-   Deletion|

