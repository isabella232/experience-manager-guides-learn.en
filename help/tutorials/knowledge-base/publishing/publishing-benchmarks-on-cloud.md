---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
---

# Guides Publishing Benchmarks on AEMaaCS

AEM Guides cloud service has some limits on publishing which Guides team is actively working to remove.

Guides team has already introduced a more scalable [Publishing microservice](publish-microservice-architecture-and-performance.md). For now, publish microservice supports only a subset of output types and support for other types is in under active development.

## Numbers

Below are the output generation numbers on AEMaaCS servers using the latest AEM Guide add-on.

>[!NOTE]
>
> The below output generation numbers have been recorded by using default DITA-OT with OOTB templates.

### AEM Site

    - Map size under test: 3250 topics
    - Time Taken for publishing: 1 Hour 27 minutes
    - Published using MicroService: No
>[!NOTE]
>
> AEM Site creates many cq:page nodes and flattens them at the same time.
> For this reason, it is advisable to avoid running multiple concurrent AEM Site publishings as it can overburden the system.

>[!NOTE]
>
> AEM Site generation time is dependent on the template used.

### Native PDF Publishing

    - Map size under test: 2500 topics
    - Time Taken for publishing: 14 minutes
    - Published using MicroService: Yes

### PDF (via DITA-OT)

    - Map size under test: 12000 topics
    - Time Taken for publishing: 16 minutes
    - Published using MicroService: Yes

### HTML

    - Map size under test: 2500 topics
    - Time Taken for publishing: 4 minutes
    - Published using MicroService: No

### Custom

    - Map size under test: 300 topics
    - Time Taken for publishing: 5 minutes
    - Published using MicroService: No

>[!NOTE]
>
> Custom publishing depends entirely on customer's own transformation logic.
