---
title: Cloud Publishing Microservice Architecture
description: Understand how the new microservice enables scalable publishing on AEMaaCS.
---

# New Cloud Publishing Microservice Architecture and Performance Data

This article share the insights into the architecture of the new publishing microservice and some performance comparisions of the new service with old cloud architecture and our on-prem offering.

## Issues with existing publishing workflows on cloud

DITA Publishing is a resource intensive process dependent mainly on available system memory and CPU. The need for these resources increases further if we are publishing large maps with many topics or if we are doing muliple parallel publishing.

If you are not using the new service then all the publishing happens on the same Kubernetes(k8) pod which is also running the AEM cloud server. A typical k8 pod has a limit on the amount of memory and CPU it can use. If AEM Guides users are publishing large or parallel workloads, this limit can breach fast. K8 restarts pods which are trying to use more resources than the configured limit which can have serious impact on the AEM cloud instance itself.

This resource constraint was the main motivation to come up with a dedicated service which can allow us to run multiple concurrent and large publishing workloads on cloud.

## Introduction to the new architecture

We are leveraging Adobe's cutting edge cloud solutions like App Builder, IO Eventing, IMS to create a serverless offering. These services are itself based on the widely accepted industry standards like Kubernetes, docker etc.

Each request to the new publishing microservice is executed in an isolated docker container which runs only one publishing request at a time. Multiple new containers will be automatically created in case new publishing requests are received. This allows us to give the best performance available to our cusotmers without introducing any security risks for our customer's content. These containers will be discarded once the publishing is over thus freeing up any used resources.

All these communications are secured by the Adobe IMS using JWT based authentication and authorization and are executed over HTTPS.

<img src="assets/architecture.png" alt="projects tab" width=600>

>[!NOTE]
>
> We do need to process some part of the publishing request on the AEM server, like dependency list generation etc for which we run an AEM job on the AEM server for each publishing request. However the most exhaustive parts of our publishing process like running DITA-OT or native engine have been offloaded to the new service.


## Running one publishing on cloud vs on-prem

If you are publishing a large map on on-prem then you might have to tweek the Java heap parameters or else you can encounter Out-of-memory errors. On cloud we have taken care of the Java heap and other configurations out of the box without you spending time in tweeking these parameters.

### Cloud

If you are executing a single publishing on cloud using the new service then publishing can take a little more time when compared to single cloud/on-prem publishing. This is due to the distributed nature of the new architecture.

<img src="assets/cloud_single_publish.png" alt="projects tab" width=600>

### On-prem

Results of single publishing will be better on old cloud architecture or on on-prem as the complete publishing is happening on the same pod/machine where AEM is running.

<img src="assets/onprem_single_publish.png" alt="projects tab" width=600>

## Running multiple publishing on cloud vs on-prem

### Cloud

This is the area where the new publishing microservice shines. As you can see from the below image, with the increase in the multiple concurrent publishing jobs, cloud is able to publish them without any significant performance degradation.

<img src="assets/cloud_bulk_publish.png" alt="projects tab" width=600>

### On-prem

Running concurrent publishing on on-prem results in severe performance degradation. This performance drop on on-prem will be even more severe if we try to publish more than 4 large maps simultaneously. If you are using the old cloud architecture then you will encounter pod restarts if you will try to publish many maps concurrently.

<img src="assets/onprem_bulk_publish.png" alt="projects tab" width=600>

## Additional Benefits

Since we need to gather dependencies to be sent to the serverless architecture for publishing, we run an AEM job on AEM instance for each publishing request.However, the new cloud architecture solely uses AEM jobs in place of AEM workflows as was the case in the old architecture. This change enables our users to individually tweek cloud publishing queue settings without impacting other AEM jobs or workflow configurations.

Details on how to configure the new publish microservice can be found here: [Configure Microservice](/configure-microservices)