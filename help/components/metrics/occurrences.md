---
title: 发生次数
description: 设置或保留变量的点击次数。
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
TQID: https://experienceleague.adobe.com/04bDCj1dkVb9gIDMbpvvGea92oOzd-N0XLfzf4t-6iA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 5e560c5a1c241a297a7bc876978f2996e793e1ea
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 66%

---

# 发生次数

“发生次数”[量度](overview.md)显示设置或持久化某个给定维度所经历的点击次数。 将工作区中的维度拖至空白画布时，Adobe 会自动将此量度应用于项目。

## 如何计算此指标

在报表包的所有点击中，包括定义或保留维度项目的点击。 某些维度（例如 [eVar](../dimensions/evar.md)）会在设定的点击之后保留。 此量度计算初始值和保留值。

## 与类似量度比较

* **发生次数与[实例](instances.md)**：发生次数计算设置或保留维度项目的点击次数。 实例不包括保留维度项目的点击。
* **发生次数与[页面查看次数](page-views.md)**：发生次数包括所有点击类型，包括页面查看跟踪调用 ([`t()`](/help/implement/vars/functions/t-method.md))、链接跟踪调用 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 和摘要[数据源](/help/import/data-sources/overview.md)中的数据。 页面查看次数量度仅包括页面查看跟踪调用，不包括链接跟踪调用和摘要数据源。

## 持久性

持久性表示给定的维度值能否在从中设置它的事件之外与指标相关。 它使用分配和有效期限的组合。 通过分配，可决定一次可在单个列中保留多个维度项时保留哪个值。 通过到期，可决定维度项目在从中设置它的事件之外保持多久。

持久性仅在维度上可用，并可追溯至应用该持久性的数据。 它是紧接应用筛选或其他分析操作之前发生的数据转换。 如果未启用持久性，则维度仅与同一事件中存在的指标相关。
