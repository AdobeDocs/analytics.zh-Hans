---
title: 数据源概述
description: 使用外部文件将数据导入Adobe Analytics。
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 数据源概述

Adobe Analytics数据源允许您导入其他在线或离线数据以便进行报告。 它们对于帮助了解网站外业务的各个方面，以及它们如何与您的网站进行交互很有价值。 使用数据源的常规工作流包含以下步骤：

1. 您的组织从其他来源收集数据。 示例包括点击前数据、呼叫中心数据或在您的网站外发生的交易的信息。
1. 数据格式化的方式与Adobe Analytics使用制表符分隔的文本文件所理解的方式相同。
1. 您可以将文本文件上传到FTP站点Adobe提供的FTP文件以及随附的 `.fin` 文件。
1. Adobe会摄取文本文件，并将该数据与网站上收集的维度和量度一起显示。

Adobe提供的数据源有两种常见类型。 所有数据源模板都基于以下两种类型之一：

* **摘要数据源**：提供了一种在Adobe Analytics中导入高级数据的简单方法。 您可以指定时间戳、变量值和关联的量度。 然后，每个维度项目的这些量度会相应增加。 如果您希望并排查看离线和在线数据，此功能很有价值。 但是，它不会将在线和离线数据链接在一起。
* **交易ID数据源**：如果由AppMeasurement发送的点击和数据源行包含匹配交易ID，则数据源中的维度和量度值将附加到该点击。

**完全处理数据源** 自2021年3月25日起，不再作为数据源类型提供。 请参阅 [生命周期结束公告](full-processing-eol.md) 了解更多信息。

Adobe还提供 [数据源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，无需使用产品UI或FTP位置即可创建数据源和上传数据。

## 后续步骤

[数据源快速入门](getting-started.md)：将简单数据源上传到开发报表包。
