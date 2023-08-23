---
title: Native PDF | Configure Node process for Native PDF Publishing
description: Configure JVM flags for Node process Publishing
---

# Configure Node Process for Native PDF Publishing

Native PDF publishing starts a separate NodeJs process to convert the files generated in the publishing process to a final PDF. You might have to tweak the configurations of this Node process running Native PDF publishing to support different scenarios. For example, to run larger workloads you should increase the maximum heap size available to the spawned NodeJs process.

Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.In the configuration file, provide the following (property) details:

|PID|Property Key|Property Value|
|---|---|---|
|`com.adobe.fmdita.config.ConfigManager`|`native.pdf.node.opts`|String value to set any standard `NODE_OPTIONS`.<BR> Default value: ""|

