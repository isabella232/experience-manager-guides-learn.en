---
title: Recommendations for performance optimization
description: Learn the Recommendations for performance optimization
---
# Recommendations for performance optimization {#id213BD0JG0XA}

## Configure data store \(Mandatory\) 

**What is the change?**
Set the `minRecordLength` property to a value of `100` under the configuration `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` For more information about file date store and S3 data store, see the [Configuring node stores and data stores in AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) article.

>[!NOTE]
>
> For S3 data store, the cost for maintaining content in data store depends on the number of requests as well. Therefore, when doing this setting with S3—setup cost per request and cache size should also be considered.

**When to configure?**
After the initial setup, but before any content is migrated. You must perform this change even on an existing system, which ensures that all new content is stored in data store instead of segment store.

**Result of this change**
The DITA files are saved in data store rather than the segment store. This keeps the segment store size under the recommended limits, which improves the responsiveness of the system.

## Update Lucene index \(Mandatory\) 

**What is the change?**
Exclude /var/dxml from oak:index/lucene.

>[!NOTE]
>
> AEM Guides never uses Lucene indexes to search for content in /var/dxml node.

**When to configure?**
If you are making this change on a new system before migrating content, then only updating oak:index/lucene is required. Otherwise, on an existing system where the content is already migrated, then after making the change in oak:index/lucene, rebuild indexes for Lucene \(*which might take few hours to complete*\).

**Result of this change**
This change prevents /var/dxml node from getting indexed and stored in the segment store.

## Java memory optimization \(Mandatory\) 

**What is the change?**
The JVM start parameters should be carefully tuned based on the infrastructure and the disk size. It is recommended that you consult Adobe Support to get help to access the ideal configuration. You may, however, try out the following configurations yourself:

– Set the JVM heap size to a minimum of 1/4th of the total available memory. Use the parameter `-Xmx<size>` to set the heap memory size. Set the value for -`Xms` equals to `-Xmx`.

– Enable `-XX:+HeapDumpOnOutOfMemoryError` and set the path for `-XX:HeapDumpPath=</path/to/folder``>`.

– Enable Java GC log as:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

– In general, for Java 11, use G1GC \(`-XX:+UseG1GC`\) and for Java 8 use CMS \(-`XX:+UseConcMarkSweepGC`\).

– Use `-XX:NewRatio` to control the size of young generation memory size. The default value is 2, which means that 1/3 of the memory is used for young generation. Since there are many objects getting quickly created and destroyed, using a value of 1 will allocate 1/2 of the memory to young generation.

– Control the number of objects being promoted to old generation using `-XX:MaxTenuringThreshold`. Use the value of 15 \(default\) to delay when objects are promoted to old generation.

**When to configure?**
If you are making this change on an existing system, you need to restart the system. In case of a fresh installation, this change should be made in the start script \(.bat or .sh\) file before the system is started.

**Result of this change**
This results in optimal heap size and regulated execution of GC.

## Client library minification on Author instance \(Optional\) 

**What is the change?**
The client libraries should be set to minify in the Authoring instances. This makes sure that there are fewer bytes to download when a user is browsing the system from different locations. To make this change, set the configuration in **HTML Library Manager** from the Felix console.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
This change improves the load time of pages on Author instance as fewer bytes are transferred for loading the client libraries.

## Configure concurrent publishing threads \(Mandatory, depending on the use case\) 

**What is the change?**
This change is required if you are using DITA-OT to publish output and a number of concurrent publishing threads is also defined.

By default, AEM Guides sets the publishing threads to the number of CPUs+1. However, it is recommended to set this value to half \(1/2\) or one-third \(1/3\) of the total number of CPUs. To do this, set the **Generation Pool Size** property under the configuration `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` as per the recommendations.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
This change ensures that on a running Author instance all resources are not allocated for the publishing operations. This keeps the system resources available for authors as well, which results in a better user experience.

## Configure batch size of nodes for AEM Site output generation \(Mandatory, depending on the use case\) 

**what is the change?**
This change is required if you are generating AEM Sites output.

Set the **Limit AEM Site Pages in Heap** property under `com.adobe.fmdita.config.ConfigManager` to a number based on your system's configuration. This property defines the batch size of nodes to be committed when the site pages are generated. For example, on a system with a larger number of CPUs and heap size, you can increase the default value from `500` to a larger number. You need to test run with the changed value to come to an optimal value for this property.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
An increased number of the **Limit AEM Site Pages in Heap** property optimizes the AEM Site output generation process.

## Optimize number of post-processing threads \(Mandatory, depending on the use case\) 

**What is the change?**
This change is required if you are bulk uploading DITA content.

Set the **Post Process Threads** property under `com.adobe.fmdita.config.ConfigManager` to `1`.

**When to configure?**
This can be done at run time.

**Result of this change**
This change reduces the post-processing time on bulk upload of DITA files.

**Parent topic:**[Download and install](download-install.md)
