---
description: 了解
title: 量度类型和归因
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 79%

---

# 量度类型和归因 {#metric-type-attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非默认的属性模型"
>abstract="为所选量度启用非默认归因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="选择量度的归因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="最后接触"
>abstract="100% 的积分归于访客看到的最后一个维度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接触"
>abstract="100% 的积分归于访客看到的第一个维度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="线性"
>abstract="积分均匀分布于所有维度值上。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="参与率"
>abstract="100% 的积分归于访客所见的每个维度值。<br/>列总数被夸大了。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予积分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="第一个维度值占 40%，最后一个维度值占 40%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="时间衰减"
>abstract="距离转化时间最近的维度值将获得最多的积分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="算法"
>abstract="积分是根据统计算法动态确定的。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顾时间范围"
>abstract="此设置可以确定将要对每次转化应用的数据归因时间窗口。"

<!-- markdownlint-enable MD034 -->

在[生成计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)时，可以指定量度类型和归因模型。

## 量度类型

要在构建计算量度时指定量度类型，请执行以下操作：

1. 选择要选择其类型的量度旁边的齿轮图标。

   ![](assets/cm_type_alloc.png)

1. 从以下选项中进行选择：

   | 指标类型 | 定义 |
   |---|---|
   | 标准 | 这些指标是在标准 [!DNL Analytics] 报表中使用的相同指标。如果公式包含一个标准指标，它会显示与其相对的非计算指标的相同数据。标准指标可用于创建特定于每个单独行项目的计算指标。例如，[订购次数]/[访问次数]是将特定行项目的订购次数除以特定行项目的访问次数。 |
   | 总计 | 在每个行项目中使用报告期间的总计。 如果公式包含一个总计指标，它会显示每个行项目的相同总数。 总计量度可用于创建与网站总计数据相比较的计算量度。 例如，[订购次数]/[总访问次数]会显示订购次数与网站所有访问次数的比例，而不只是与特定行项目访问次数的比例。 |

## 线性分配的工作方式

[归因](/help/analyze/analysis-workspace/attribution/overview.md)是计算指标中分配模型的评估方式。

有关支持的非默认归因模型和回溯时段的完整列表，请参阅[归因模型和回溯时段](/help/analyze/analysis-workspace/attribution/models.md)。

以下示例说明了具有线性分配的计算指标在报表中的工作方式：

| | 第 1 次点击 | 第 2 次点击 | 第 3 次点击 | 第 4 次点击 | 第 5 次点击 | 第 6 次点击 | 第 7 次点击 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| 发送的数据 | 促销活动 A | - | 促销活动 A | 促销活动 B | - | 促销活动 C | $10 |
| 最近联系 eVar | 促销活动 A | 促销活动 A | 促销活动 A | 促销活动 B | 促销活动 B | 促销活动 C | $10 |
| 首次联系 eVar | 促销活动 A | 促销活动 A | 促销活动 A | 促销活动 A | 促销活动 A | 促销活动 A | $10 |
| 示例 Prop | 促销活动 A | - | 促销活动 A | 促销活动 B | - | 促销活动 C | $10 |

此示例中，在第 7 次点击进行了价值 10 美元的购买之前，值 A、B、C 已发送到第 1、3、4、6 次点击上的变量之中。第二行显示出，在这一系列的点击中，这些值均一直持久出现在最近联系访问中。第三行则显示出首次联系访问的持久性。最后，最后一行显示的是某个不具有持久性的属性 (Prop) 其数据是如何记录的。

