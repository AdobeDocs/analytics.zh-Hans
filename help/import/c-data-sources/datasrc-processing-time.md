---
description: 'null'
title: 数据源处理时间
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '119'
ht-degree: 100%

---


# 数据源处理时间

>[!NOTE]
>任何数据处理时间段都应视为粗略估计值，不构成服务级别协议 (SLA)。

数据处理时间不尽相同，具体原则如下所示：

* 当天的数据：将在数据上载后约 2 个小时内完成处理。
* 前一天的数据：将在数据上载后约 3 个小时内完成处理。

所上载数据的日期每往前推一天，处理时间将增加约 1 个小时，最多可增加 17 个小时。

例如，如果您上载的是前一天的数据，那么约 2 小时后可在 Analytics 中看到该数据。如果您上载的是上个月的数据，那么约 17 小时后可在 Analytics 中看到该数据。
