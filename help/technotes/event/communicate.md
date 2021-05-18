---
title: 向用户传达影响
description: 了解传达事件在您组织中的影响的有效方式。
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# 向用户传达事件影响

如果您的数据[受事件](overview.md)影响，请务必将该事件通信给组织中的用户。

* 制定可在通信中使用的共同免责声明，以实现一致性
* 在事件期间和之后，向Analytics用户和关键利益相关方提供持续沟通
* 为后续里程碑（如下月或年）放置日历提醒。 此通信将来有助于提醒查看报表的用户按月或按年报告的影响。

在Adobe Analytics中，以下部分显示了您与组织内用户进行通信的不同方式。 您还可以使用Adobe Analytics以外的其他方法（如电子邮件）与用户进行通信。

## 通过面板或可视化描述进行通信

如果您的组织中的用户共享了Workspace项目，则可以通过面板或可视化描述来交流事件的影响。 右键单击面板或可视化标题，然后选择&#x200B;**[!UICONTROL 编辑说明]**。

![面板说明](assets/panel_description.png)

## 通过文本可视化进行交流

您还可以通过专用的文本可视化来传达事件的影响。 请参阅《分析用户指南》中的[文本可视化](/help/analyze/analysis-workspace/visualizations/text.md)。

![文本可视化](assets/text_visualization.png)

## 将自定义日历事件添加到Workspace中的趋势

对于Workspace中的任何趋势可视化，您可以添加一个表示受影响日期范围的系列。

1. 通过遵循[排除分析](segments.md)中的特定日期，创建具有“受影响的天数”区段的计算量度。
1. 将所需量度添加到计算量度画布。

   ![量度](assets/calcmetric_event.png)

1. 添加标题和说明，以告知用户影响。 如果需要，您还可以将此量度标记为日历注释。

   ![标题和描述](assets/calcmetric_title_description.png)

1. 在自由格式表中，添加“Day”维。 将“访问”和您的计算量度并列添加。

   ![自由格式表](assets/calcmetric_freeform.png)

1. 单击计算量度的列设置齿轮图标，然后启用&#x200B;**[!UICONTROL 将零解释为无值]**。

   ![计算量度设置](assets/calcmetric_zero_no_value.png)

1. 添加线条可视化。 受影响的日子用不同的颜色表示。 用户还可以单击计算量度中的“信息”图标以了解更多信息。

   ![信息图标](assets/calcmetric_infoicon.png)

## 在Reports &amp; Analytics中使用日历事件

如果您使用Reports &amp; Analytics，则可使用[日历事件](/help/components/t-calendar-event.md)来突出显示任何趋势报表中受影响的天数。 此方法不适用于Analysis Workspace。

1. 导航到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 所有组件]** > **[!UICONTROL 日历事件]**。
2. 输入所需的标题、日期范围和附注文本。
3. 单击&#x200B;**[!UICONTROL 保存]**。

![日历事件](assets/exclude_calendar_event.png)
