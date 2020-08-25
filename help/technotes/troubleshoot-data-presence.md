---
title: 数据存在疑难解答
description: 了解在报告中看不到数据时可以采取哪些步骤。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---


# 数据存在疑难解答

在Analysis Workspace，一些项目设置返回零行。 在Reports &amp; Analytics中，查看某些报表会返回以下消息：

**“没有选定标准的数据。”**

使用以下步骤确定报表不显示数据的原因。

## 数据存在，但已过滤掉

您的报表包包含数据，但报表中使用的特定组件会过滤器所有数据。

* **细分**:区段可轻松阻止所有数据显示在报表中。 检查所有区段定义并删除所有区段，以查看区段是否导致数据不显示。
* **指标**:检查以确保使用了正确的度量。 将度量更改 [为](/help/components/metrics/occurrences.md) “发生次数”，以确保该度量不是没有数据的报表的参与者。
* **日期范围**:过去或将来的任何时间，日期范围都过长不会返回数据。 贵组织的数据保 [留策略决定](data-retention.md) ，保留的备份数据的距离。
* **过滤器**:从报表中删除所有搜索过滤器。

## 数据不存在

如果没有区段，则度量为“发生次数”，日期范围为当月，并且没有搜索过滤器，请检查以下内容：

* **验证报表包**:确保您位于包含数据的报表包中。 许多组织都有新的、测试或开发报告套件，它们通常不包含很多数据。
* **延迟**:如果查看最新数据，则数据可能会延迟。 请参 [阅延迟](latency.md) ，以了解详细信息。
* **验证数据收集**:导航到报表包应跟踪的Web属性，然后打开 [Adobe调试器](https://docs.adobe.com/content/help/zh-Hans/debugger/using/experience-cloud-debugger.html)。 确保在加载页面时存在Analytics图像请求。 如果您看到图像请求，请确保它使用正确的报表包ID，它包含有效 [的currencyCode](/help/implement/vars/config-vars/currencycode.md)，并且该 [时间戳支持](/help/implement/vars/page-vars/timestamp.md) 在图像请求和报表包之间匹配。
