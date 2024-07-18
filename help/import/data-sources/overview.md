---
title: 数据源概述
description: 使用外部文件将数据导入Adobe Analytics。
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# 数据源概述

Adobe Analytics数据源允许您导入其他在线或离线数据以便进行报告。 它们对于帮助了解网站外部业务的各个方面以及它们如何与您的网站交互很有价值。 使用数据源的常规工作流包含以下步骤：

1. 您的组织从其他来源收集数据。 例如，点击前数据、呼叫中心数据或在您的网站外发生的交易信息。
1. 数据格式化的方式与Adobe Analytics使用制表符分隔的文本文件所理解的方式相同。
1. 您将文本文件上传到Adobe提供的FTP站点，以及随附的`.fin`文件。
1. Adobe会摄取文本文件，并将该数据与网站上收集的维度和量度一起显示。

Adobe提供两种常见的数据源类型。 所有数据源模板均基于以下两种类型之一：

* **摘要数据源**：提供了一种在Adobe Analytics中导入高级数据的简单方法。 您可以指定时间戳、变量值和关联的量度。 然后，每个维度项目的这些量度会相应地增加。 如果您希望并排查看离线和在线数据，此功能很有价值。 但是，它不会将在线和离线数据链接在一起。
* **交易ID数据源**：如果AppMeasurement发送的点击和数据源行包含匹配的交易ID，则数据源中的维度和度量值将附加到该点击。

**自2021年3月25日起，不再将Full processing data sources**&#x200B;作为数据源类型提供。 有关详细信息，请参阅[生命周期结束公告](full-processing-eol.md)。

Adobe还提供[数据源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，它允许您在不使用产品UI或FTP位置的情况下创建数据源和上传数据。

## 后续步骤

[数据源入门](getting-started.md)：将简单数据源上传到开发报表包。
