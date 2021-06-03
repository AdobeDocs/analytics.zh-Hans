---
title: 数据存在疑难解答
description: 了解在报表中看不到数据时可以采取哪些步骤。
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 1%

---


# 数据存在疑难解答

在Analysis Workspace中，某些项目设置会返回零行。 在Reports &amp; Analytics中，查看某些报表会返回以下消息：

**“没有选定标准的数据。”**

请按照以下步骤确定报表不显示数据的原因。

## 数据存在，但已过滤掉

您的报表包中包含数据，但报表中使用的特定组件会过滤掉所有数据。

* **区段**:区段可以轻松阻止所有数据显示在报表中。检查所有区段定义并删除所有区段，以查看区段是否导致数据不显示。
* **量度**:检查以确保使用了正确的量度。将量度更改为[发生次数](/help/components/metrics/occurrences.md)，以确保该量度不是没有数据的报表的参与者。
* **日期范围**:过去或未来任何时间过长的日期范围不会返回数据。贵组织的[数据保留策略](data-retention.md)确定保留数据的时长。
* **过滤器**:从报表中删除所有搜索过滤器。

## 数据不存在

如果没有区段，则量度为发生次数，日期范围是当前月份，并且没有搜索过滤器，请检查以下各项：

* **验证报表包**:确保您位于包含数据的报表包中。许多组织都有新的、测试或开发报表包，这些报表包通常不包含大量数据。
* **延迟**:如果查看最近的数据，则数据可能会延迟。有关更多信息，请参阅[延迟](latency.md) 。
* **验证数据收集**:导航到您的报表包应跟踪的Web属性，然后打开 [Adobe调试器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)。确保在加载页面时存在Analytics图像请求。 如果您看到图像请求，请确保它使用正确的报表包ID，它包含有效的[currencyCode](/help/implement/vars/config-vars/currencycode.md)，并且图像请求和报表包之间的[时间戳支持](/help/implement/vars/page-vars/timestamp.md)匹配。
