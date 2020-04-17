---
title: 分析受事件影响的数据
description: 了解受事件影响的数据对整体数据质量的贡献。
translation-type: tm+mt
source-git-commit: e3360e15de14f594e62b4be6316f8b095091ec1f

---


# 分析受事件影响的数据

有时，事件会影响组织中的数据质量。 示例包括：

* 发送异常数据的机器人，如数百万美元的收入
* 贵组织向您的网站推送了更新，该更新对Analytics实施产生负面影响
* 影响服务器质量的中断，无论是在您的组织端还是Adobe端

如果您的网站遇到数据质量问题、实施问题或数据中的其他差距，您可能希望将其排除在报告之外，以防止对部分数据做出决策。 使用这些部分来评估事件对数据的影响，并确定您要继续的方式。

## 使用细分分析和排除数据

Adobe Analytics优惠了一种简单而可靠的方法，可使用细分来集中处理或排除数据。 您可以使用区段中的日期范围维度筛选掉这些特定日期或将注意力集中在这些特定日期。 请参 [阅组件用户指南中的分析](/help/components/c-segmentation/use-cases/exclude-date-range.md) “排除特定日期”。

## 将事件与先前的日期范围进行比较

如果您想进一步了解一段时间内事件对数据的影响，可以在分析工作区中使用日期比较。 利用此功能，您可以逐日、逐周或逐月比较数据，以了解数据与先前范围的比较情况。 然后，您可以使用此比较来确定事件对趋势的影响程度。 请参 [阅分析用户指南中比较受事件影响的日期](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) ，以前的范围。

## 在Reports &amp; Analytics中使用日历事件

如果您使用Reports &amp; Analytics，则可以使用日历 [事件](/help/components/t-calendar-event.md) ，在任何趋势报告中突出显示受影响的日期。 此方法不适用于分析工作区。

1. 导航到 **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**。
2. 输入所需的标题、日期范围和附注文本。
3. 单击 **[!UICONTROL Save]**.

![日历事件](assets/exclude_calendar_event.jpg)
