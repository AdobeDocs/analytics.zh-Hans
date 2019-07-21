---
description: 捕捉特定值的次数加上保留给定值的页面查看数量。也就是说，发生次数是页面查看次数和页面事件数之和。发生次数适用于 Analysis Workspace 和 Ad Hoc Analysis。
seo-description: 捕捉特定值的次数加上保留给定值的页面查看数量。也就是说，发生次数是页面查看次数和页面事件数之和。发生次数适用于 Analysis Workspace 和 Ad Hoc Analysis。
seo-title: 发生次数
solution: Analytics
title: 发生次数
topic: 量度
uuid: ff999fba-fcb7-4b16-944-001facd0 f15 d
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# 发生次数

捕捉特定值的次数加上保留给定值的页面查看数量。也就是说，发生次数是页面查看次数和页面事件数之和。发生次数适用于 Analysis Workspace 和 Ad Hoc Analysis。

## 比较实例数和发生次数 {#section_4B0741AC1A78456E98AE0D4D28D70D29}

下面列出了两个相似的量度：

**[实例数](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)**：针对变量设置某个值的次数。

**发生次数**：设置或持续某个值的总次数。

| 情况 | 描述 |
|---|---|
| 发生次数高于实例数 | 对于转化变量，通常会出现这种情况，因为发生次数也包含定义变量的次数（实例数）。 |
| 实例数高于发生次数 | 在报表中不可能出现这种情况，因为所有实例同时也会被记录为发生次数。 |
| 实例数等于发生次数 | 对于流量变量，这是最常见的，因为通常情况下它们无法独立于图像请求之外存在。 |

>[!MORE_LIKE_THIS]
>
>* [实例](/help/components/c-variables/c-metrics/metrics-instance.md)

