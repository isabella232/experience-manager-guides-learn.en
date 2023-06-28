---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
exl-id: cc6e38b9-6276-4147-beda-93f66368e15d
---
# AEM Guides Publishing Benchmarks on AEMaaCS

Currently AEM Guides cloud service has some limits on publishing map sizes which Guides team is actively working to resolve.

Guides team has already introduced a scalable Publishing Microservice to support large maps and multiple concurrent publishing. To understand [publishing microservice architecture] refer(publish-microservice-architecture-and-performance.md)

To configure the new publishing service for any AEM cloud environment refer [Configure new microservice-based publishing](configure-microservices.md)


## Execution Environment

    AEM Release: 2023.5.11983.20230511T173830Z
    Guide Add On Release: 2023.6.0
    AEM Site Template: AEM Guides OOTB template
    DITA-OT version: 3.5.4
    Publish Workflow Type: Split Publish Workflow
    Output supported by microservice: Native PDF, PDF (Dita-OT)

## Output Generation Numbers

| Output Type   | Map Size (Topic References)  | Execution Time (in Seconds)|Publishing Microservice|
|---------------|------------------------------|----------------------------|-----------------------|
| AEM Site      | 3500                         |    5220                    | No                    |
| Native PDF    | 3500                         |    780                     | Yes                   |
| PDF (DITA-OT) | 11000                        |    960                     | Yes                   |
| HTML5         | 3500                         |    240                     | No                    |
| Custom        | 300                          |    300                     | No                    |

## Key points to remember

- AEM Site creates many cq:Page nodes and flattens by rendering them individually during generation time. For this reason, it is advisable to avoid running large multiple concurrent AEM Site publishings as it can overburden the system.
- AEM Site generation time depends on the template used. Execution time can increase if complex template is used.
- Custom publishing execution time is for a sample custom output. Custom publishing time solely depends  on customer's own transformation logic.
