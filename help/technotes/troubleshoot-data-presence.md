---
title: 数据状态疑难解答
description: 了解当您在报表中看不到数据时可以采取的具体步骤。
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---


# 数据状态疑难解答

在 Analysis Workspace 中，某些项目设置会返回零行。在 Reports &amp; Analytics 中，查看某些报表会返回以下消息：

**“没有适合选定标准的数据。”**

使用以下步骤确定报表不显示数据的原因。

## 数据存在但被过滤掉了

您的报表包包含数据，但报表过滤器中使用的特定组件会过滤掉所有数据。

* **区段**：区段可以轻松防止所有数据都出现在报表中。检查所有区段定义并删除所有区段以查看区段是否导致您的数据不显示。
* **量度**：检查以确保使用正确的量度。将量度更改为[发生次数](/help/components/metrics/occurrences.md)，以确保该量度不是无数据的报表的投稿人。
* **日期范围**：过去太久或将来任何时间的日期范围都不会返回数据。您组织的[数据保留策略](data-retention.md)决定了保留多旧的数据。
* **过滤器**：从报表中删除所有搜索过滤器。

## 数据不存在

如果没有区段，量度是“发生次数”，日期范围是当月，并且没有搜索过滤器，请检查以下内容：

* **验证报表包**：确保您所使用的报表包中包含数据。许多组织具有通常不包含太多数据的全新、测试或开发报表包。
* **延迟**：如果查看最近的数据，则数据可能只是延迟了。有关详细信息，请参阅[延迟](latency.md)。
* **验证数据收集**：导航到您的报表包应该跟踪的 Web 属性，然后打开 [Adobe 调试器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)。确保加载页面时存在 Analytics 图像请求。如果您看到图像请求，请确保它使用正确的报表包 ID，包括有效的 [currencyCode](/help/implement/vars/config-vars/currencycode.md)，并且[时间戳支持](/help/implement/vars/page-vars/timestamp.md)在图像请求和报表包之间匹配。
