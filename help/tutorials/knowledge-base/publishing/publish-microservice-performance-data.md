---
title: Publishing microservice performance data
description: Understand how the new microservice enables scalable publishing on AEMaaCS.
---

## Issues with existing publishing workflows on cloud
Publishing is a resource intensive process. The need for system resources like memory increases further if we are publishing large maps or are doing muliple concurrent publishing.


If you are not using the new service then all the publishing will happen on the same Kubernetes(k8) pod which is also running the AEM server. A typical k8 pod has a limit on the amount of memory & CPU it can use. If AEM guides users are publishing large workloads, this limit can breach fast. K8 restarts pods which are trying to use more resources than the configured limit. 

This resource constraint was the main motivation to come up with a dedicated service which can allow us to run multiple concurrent and large workloads on cloud.

## Introduction on the new architecture
We are levraging the cutting edge Adobe cloud solutions like App Builder, IO Eventing to create serverless offering. This new publishing microservice runs on a new isolated docker container which runs only one publishing at a time. 

This allows us to give the best performance available to our cusotmers without introducing any security risks for our customer's content. If users are running multiple publishing then our Adobe's serverless platfom will create multiple containers. These containers will be discarded once the publishing is over.

<img src="assets/architecture.png" alt="projects tab" width=500>

## Running one publishing on cloud vs on-prem
If you are publihing a large map on on-prem then you might have to tweek the heap parameters or else you can encounter out of memory errors. On cloud we have taken care of the heap configurations without spending time in tweeking the memory parameters.

If you are executing a single publishing on cloud using the new service then publishing can take a little more time. This is due to the distributed nature of the new architecture. 

### Cloud
<img src="assets/cloud_single_publish.png" alt="projects tab" width=500>

### On-prem
<img src="assets/onprem_single_publish.png" alt="projects tab" width=500>


## Running multiple publishing on cloud vs on-prem
This is the area where the new publishing microservice shines. As you can see from the below images, with the increase in the multiple publishing jobs, cloud is able to publishing them without any significant performance degradation.

### Cloud
<img src="assets/cloud_bulk_publish.png" alt="projects tab" width=500>

### On-prem
<img src="assets/onprem_bulk_publish.png" alt="projects tab" width=500>

Running concurrent publishing on on-prem results in severe performance degradation but cloud scales thus it does not result in any significant performance drop.

This performance drop on on-prem will be even more severe if we try to publish more than 4 large maps simultaneously.

By this we can say that the power of the new cloud publishing lies in its ability to scale and thus giving our users optimum experience even if they are running large workloads concurrently.

Details on how to configure the new publish microservice can be found here: [Configure Microservice](/configure-microservices)