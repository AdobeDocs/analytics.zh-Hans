---
title: 数据源概述
description: 使用外部文件将数据导入Adobe Analytics。
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 数据源概述

Adobe Analytics数据源允许您导入其他在线或离线数据以进行报告。 它们对于帮助了解网站外的业务方面以及它们与网站的交互方式非常有用。 使用数据源的常规工作流包含以下步骤：

1. 贵组织从其他来源收集数据。 示例包括预点击数据、呼叫中心数据或有关网站外发生的交易的信息。
1. 数据的格式设置方式与Adobe Analytics了解的使用制表符分隔的文本文件的格式一致。
1. 您将文本文件上传到FTP站点Adobe提供的，以及 `.fin` 文件。
1. Adobe会摄取文本文件，并在网站上收集的维度和量度旁边显示该数据。

有两种Adobe选件的常规数据源类型。 所有数据源模板都基于以下两种类型之一：

* **概要数据源**:为在Adobe Analytics中导入高级别数据提供了一种简单的方法。 您可以指定时间戳、变量值和关联的量度。 然后，每个维度项目的这些量度会相应地增加。 如果您想要并排查看离线和在线数据，则此功能很有价值。 但是，它不会将在线和离线数据链接在一起。
* **交易ID数据源**:如果由AppMeasurement发送的点击和数据源行包含匹配的交易ID，则数据源中的维度和量度值会附加到该点击。

**完全处理数据源** 自2021年3月25日起不再提供为数据源类型。 请参阅 [生命周期终止公告](full-processing-eol.md) 以了解更多信息。

Adobe还提供 [数据源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，以便您无需使用产品UI或FTP位置即可创建数据源并上传数据。

## 后续步骤

[数据源入门](getting-started.md):将简单的数据源上载到开发报表包。
