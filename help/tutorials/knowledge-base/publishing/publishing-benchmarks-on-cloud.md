---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
---

# AEM Guides Publishing Benchmarks on AEMaaCS

Currently AEM Guides cloud service has some limits on publishing map sizes which Guides team is actively working to resolve.

Guides team has already introduced a scalable [Publishing Microservice](publish-microservice-architecture-and-performance.md) to support large maps and multiple concurrent publishing. For now, this publish microservice supports a subset of output types and support for other types is in under active development and will be available soon.

To configure the new publishing service for any AEM cloud environment please refer [Configure new microservice-based publishing] (knowledge-base/publishing/configure-microservices.md)

Below are the output generation numbers on AEM Guides cloud service server.

## Execution Environment

    AEM Release: 2023.6.39380.20230608T144106Z
    Guide Add On Release: 2023.6.0
    AEM Site Template: AEM Guides OOTB template
    DITA-OT version: 3.5.4


## Output Generation Numbers

| Output Type   | Map Size (Topic References)  | Execution Time (in Seconds)|
|---------------|------------------------------|----------------------------|
| AEM Site      | 3250                         |    5220                    |
| Native PDF    | 3250                         |    780                     |
| PDF (DITA-OT) | 11000                        |    960                     |
| HTML5         | 2500                         |    240                     |
| Custom        | 300                          |    300                     |


## Key points to remember

-  AEM Site creates many cq:Page nodes and flattens by rendering them individually during generation time. For this reason, it is advisable to avoid running large multiple concurrent AEM Site publishings as it can overburden the system.
-  AEM Site generation time depends on the template used. Execution time can increase if complex template is used.
-  Custom publishing execution time are for a sample custom output. Custom publishing time solely depends  on customer's own transformation logic.
