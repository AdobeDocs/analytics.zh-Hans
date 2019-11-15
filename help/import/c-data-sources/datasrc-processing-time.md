---
description: 'null'
solution: Analytics
title: 数据源处理时间
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 数据源处理时间

>[!Note]
>任何数据处理时间段都应视为近似的，不构成服务级别协议(SLA)。

数据处理时间不尽相同，具体原则如下所示：

* 当日数据：在上传数据约2小时后，处理完成。
* 前一天的数据：将在数据上载后约 3 个小时内完成处理。

所上载数据的日期每往前推一天，处理时间将增加约 1 个小时，最多可增加 17 个小时。

例如，如果您上载的是前一天的数据，那么约 2 小时后可在 Analytics 中看到该数据。如果您上载的是上个月的数据，那么约 17 小时后可在 Analytics 中看到该数据。
