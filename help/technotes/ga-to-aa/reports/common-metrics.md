---
title: 其他平台上常用的指标翻译指南
description: 了解如何使用Google Analytics用户更熟悉的术语提取许多常见报告的度量数据。
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# 其他平台上常用的指标翻译指南

在Google Analytics等其他平台上，许多报告共享的指标数很多。 使用此页可了解如何重新创建在许多报告中使用的度量。

要向工作区自由格式表添加多个度量，请将度量从工作区中度量标题旁边的组件区域拖动：

![其他指标](/help/technotes/ga-to-aa/assets/new_metric.png)

## 客户赢取量度

**用户** ，大约等于工作 **区中的** “唯一访客”。 有关更多详 [细信息，请参阅组件用户指南中的](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) “唯一访客”量度。

**新用户** ，可通过以下方式获取：

1. 将“独 **特访客** ”量度拖动到工作区上。
2. 将“首次 **访问”区段拖至** “唯一访客”量度标题上方：

   ![首次访问量](../assets/first_time_visits.png)

**会话** ，与Analysis Workspace中的 **访问** (Visits)大致相等。 有关更多 [详细信息](/help/components/c-variables/c-metrics/metrics-visit.md) ，请参阅组件用户指南中的访问量度。

![客户赢取量度](../assets/acquisition_metrics.png)

## 行为指标

**跳出率** （Analysis Workspace中提供的跳出率）可作为指标。 有关其他 [信息，请参阅组件用户指南中的](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) “跳出率”量度。

**页面／会话** 是一个计算量度。 它可以通过以下方式获得：

1. 如果您已经创建此计算量度，请在“量度”下找到它，然后将其拖动到工作区上。
2. 如果尚未创建此计算量度，请单击量度列表 **旁的+** 图标以打开“计算量度生成器”。
3. 为其提供标题“每次访问的页面查看次数”，并根据需要提供说明。
4. 将格式设置为“小数”，将小数位数设置为2。
5. 将“页面 **查看次数** ”量度和“ **访问次数** ”量度拖入定义区域。
6. 排列定义，使公式为“页面 **查看次数”除以“访问次数”**。

   ![每次访问的页面查看次数](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. 单击“保存”返回工作区。
8. 将新定义的计算量度拖动到工作区上。

   了解有关“组 [件”用户指南](/help/components/c-variables/c-metrics/calculated-metric.md) “计算量度”的更多信息。

**平均会话持续时间** ，大约等于每 **次访问所花费的时间（秒）**。 了解有关“组 [件”用户指南中](/help/components/c-variables/c-metrics/metrics-time-spent.md) “停留时间”指标的更多信息。

## 转化率指标

**目标转化率**、目 **标完成**、目标值要 **** 求在这两个平台上实施更多。 如果您的实施已经包含产品维度和购买事件，请考虑以下步骤：

1. 将“订 **单** ”量度、“收 **入”量度和** “访问 **”量度拖** 动到工作区。
1. 创建每次访问的订 **单的计算量度**。 在两个度量标题上使用Ctrl+单击(Windows)或Cmd+单击(Mac)可高亮显示它们。 右键单击其中一个标题，选择从选 **择创建度量**，然后单击 **划分**。 此新指标与目标转化率相似。
1. 如果需要小数位，请编辑“计算量度”。 单击度量标题中的“信息”按钮，然后单击铅笔图标。 在“计算量度生成器”窗口中添加1位或2位小数，然后单击“保存”。

   ![每次访问的订单数](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

如果您的实施尚未包含产品或转化数据，Adobe建议与实施顾问合作，确保数据质量和完整性。
