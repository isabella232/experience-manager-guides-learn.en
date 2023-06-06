---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
---

# Guides Publishing Benchmarks on AEMaaCS
AEM Guides cloud service has some limits on publishing which Guides team is actively working to remove. 

Guides team has already introduced a more scalable [Publishing microservice](publish-microservice-architecture-and-performance.md). For now it supports only a subset of output types and soon will support other output types as well.

## Numbers

Below are the typlical output generation numbers on AEMaaCS servers. It is expected that customer content will take similar amout of time when executed on customer environments.

### AEM Site

    - Map Size under test: 2500
    - Time Taken for publishing: 14 minutes
    - Published using MicroService: No
### Native PDF Publishing

    - Map Size under test: 2500
    - Time Taken for publishing: 13 minutes
    - Published using MicroService: Yes
### PDF (via DITA-OT)

    - Map Size under test: 12000
    - Time Taken for publishing: 16 minutes
    - Published using MicroService: Yes
### HTML

    - Map Size under test: 
    - Time Taken for publishing:
    - Published using MicroService: No
### Custom

    - Map Size under test: 2500
    - Time Taken for publishing: 15 minutes
    - Published using MicroService: No
### EPUB

    - Map Size under test: 2500
    - Time Taken for publishing: 15 minutes
    - Published using MicroService: No
