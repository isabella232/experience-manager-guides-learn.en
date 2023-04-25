---
title: Publishing microservice performance data
description: Understand how the new microservice enables scalable publishing on AEMaaCS.
---

## Issues with existing publishing workflows on cloud
Publishing is a resource intensive process. The need for resources like memory also increases as the size of the map being published increases. 


A typical cloud k8 pod has a limit on the amount of memory & CPU it can use. If AEM guides users are doing multiple concurrent publishing or are publishing large maps this limit can breach fast. Kubernetes restarts such pods which are trying to use more that allowed resources. 

This resource constraint was the main motivation to come up with a dedicated service which can allow us to run multiple concurrent and large workloads on cloud.

## Introduction on the new architecture
We are levraging the cutting edge Adobe cloud solutions like App Builder, IO Eventing to create serverless offering. This new publishing microservice runs on a new isolated container which runs only one publishing at a time. 

This allows us to give the best performance available to our cusotmers without introducing any security risks for our customer content.


## Running one processing on cloud vs on-prem
From the below images we can see that if we are running just one processing on cloud then it will have some performance degradation when we compare it with single on-prem publishing.

### Cloud
<img src="assets/cloud_single_publish.png" alt="projects tab" width=500>

### On-prem
<img src="assets/onprem_single_publish.png" alt="projects tab" width=500>

This is because on cloud we are running everything on a distributed environment where we have to perform large amounts of downloading and uploading of assets thus resulting in some additional processing time.

## Running multiple processing on cloud vs on-prem
From the below images we can see that even if we are running 3-4 simultaneous publishing jobs then cloud shines when compared to on-prem.

### Cloud
<img src="assets/cloud_bulk_publish.png" alt="projects tab" width=500>
### On-prem
<img src="assets/onprem_bulk_publish.png" alt="projects tab" width=500>

Running concurrent publishing on on-prem results in severe performance degradation but cloud scales thus it does not result in any significant performance drop.


This performance drop on on-prem will be even more severe if we try to publish more than 4 large maps simultaneously.


By this we can say that the power of the new cloud publishing lies in its ability to scale and thus giving our users optimum experience even if they are running large workloads concurrently.