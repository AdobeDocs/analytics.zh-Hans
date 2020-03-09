---
title: 其他平台上常用的量度翻译指南
description: 了解如何使用 Google Analytics 用户更熟悉的术语提取许多常见报表的量度数据。
translation-type: ht
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# 其他平台上常用的量度翻译指南

在 Google Analytics 等其他平台上，许多报表共享相同数量的量度。通过本页面可了解如何重新创建用于许多报表的量度。

要向工作区自由格式表添加多个量度，请从工作区中量度标题旁边的组件区域拖动量度：

![其他量度](/help/technotes/ga-to-aa/assets/new_metric.png)

## 客户获取量度

**用户**&#x200B;大致相当于 Workspace 中的&#x200B;**独特访客**。有关更多详细信息，请参阅组件用户指南中的[独特访客](/help/components/c-variables/c-metrics/metrics-unique-visitors.md)。

可通过以下方式获取&#x200B;**新用户**：

1. 将&#x200B;**独特访客**&#x200B;量度拖动到工作区。
2. 将&#x200B;**第一次访问**&#x200B;区段拖动到“独特访客”量度标题上方：

   ![第一次访问](../assets/first_time_visits.png)

**会话次数**&#x200B;大致相当于 Analysis Workspace 中的&#x200B;**访问次数**。有关更多详细信息，请参阅组件用户指南中的[访问次数](/help/components/c-variables/c-metrics/metrics-visit.md)量度。

![客户获取量度](../assets/acquisition_metrics.png)

## 行为量度

**跳出率**&#x200B;可在 Analysis Workspace 中作为量度使用。有关更多信息，请参阅组件用户指南中的[跳出率](/help/components/c-variables/c-metrics/metrics-bounce-rate.md)量度。

**页面/会话**&#x200B;是一个计算量度。可以通过以下方式获得：

1. 如果您已经创建此计算量度，请在“量度”下找到它，然后将其拖动到工作区。
2. 如果尚未创建此计算量度，请单击量度列表旁边的 **+** 图标以打开“计算量度生成器”。
3. 将其标题命名为“每次访问的页面查看次数”，并根据需要提供说明。
4. 将格式设置为“小数”，将小数位数设置为 2。
5. 将&#x200B;**页面查看次数**&#x200B;量度和&#x200B;**访问次数**&#x200B;量度拖动到定义区域。
6. 排列定义，使公式为&#x200B;**页面查看次数除以访问次数**。

   ![每次访问页面查看次数](/help/technotes/ga-to-aa/assets/page_views_per_visit.png)

7. 单击“保存”以返回工作区。
8. 将新定义的计算量度拖动到工作区上。

   您可在组件用户指南中了解有关[计算量度](/help/components/c-variables/c-metrics/calculated-metric.md)的更多信息。

**平均会话持续时间**&#x200B;大致相当于&#x200B;**每次访问逗留时间（秒）**。您可在组件用户指南中了解有关[逗留时间](/help/components/c-variables/c-metrics/metrics-time-spent.md)的更多信息。

## 转化率量度

**目标转化率**、**目标完成率**&#x200B;和&#x200B;**目标值**&#x200B;在这两个平台上都需要额外的实施。如果您的实施已经包含产品维度和购买事件，请考虑执行以下步骤：

1. 将&#x200B;**订单**&#x200B;量度、**收入**&#x200B;量度和&#x200B;**访问次数**&#x200B;量度拖动到到工作区。
1. 创建&#x200B;**每次访问的订单数**&#x200B;的计算量度。按住 ctrl 并单击 (Windows) 或按住 cmd 并单击 (Mac) 两个量度标题以高亮显示它们。右键单击其中一个标题，选择&#x200B;**通过所选内容创建量度**，然后单击&#x200B;**除**。此新量度与“目标转化率”相似。
1. 如果需要小数位，请编辑“计算量度”。单击量度标题中的“信息”按钮，然后单击铅笔图标。在“计算量度生成器”窗口中添加 1 位或 2 位小数，然后单击“保存”。

   ![每次访问的订单数](/help/technotes/ga-to-aa/assets/orders_per_visit.png)

如果您的实施尚不包含产品或转化数据，Adobe 建议与实施顾问合作，确保数据质量和完整性。
