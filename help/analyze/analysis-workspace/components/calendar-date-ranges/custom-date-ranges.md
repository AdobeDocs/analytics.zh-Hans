---
description: 在 Analysis Workspace 中创建自定义日期范围，并将它们另存为“时间”组件。
keywords: Analysis Workspace
title: 创建自定义日期范围
feature: Calendar
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---

# 创建自定义日期范围

在 Analysis Workspace 中创建自定义日期范围，并将它们另存为“时间”组件。

**[!UICONTROL 组件]** > **[!UICONTROL 新建日期范围]**

日期范围应用于面板级别。要在项目中添加日期范围，请单击&#x200B;**面板** > *`<select panel>`*，然后指定一个新的日期范围。

## “两个月之前”的日期范围 {#section_C4109C57CB444BB2A79CC8082BD67294}

下面的自定义日期范围显示了“两个月之前”的日期范围，其中，“概要更改”可视化信息显示了方向上的变化。

![](assets/date-range-two-months-ago.png)

自定义日期范围显示在项目中“日期范围”组件面板的最上方：

![](assets/date-range-panel-two-months-ago.png)

您可以将这个自定义日期范围拖至使用“上个月”预设的自定义月连续日期范围旁边的列中，以便进行比较。添加一个“概要更改”可视化图表并从每个列中选择总量，可显示方向上的变化：

![](assets/date-range-two-months-table.png)

## 使用 7 天滚动日期范围 {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

日期范围应用于面板级别。若要在项目中添加日期范围，请单击&#x200B;**操作** > **添加面板**，然后指定一个新的日期范围。

在“日期范围生成器”中，您可以创建一个与其他日期范围一同显示在“组件”面板中的自定义日期范围。

例如，您可以创建一个日期范围，指定一个于一周前结束的连续 7 天的时段。

![](assets/create_date_range.png)

使用 *`rolling daily`*。

* “开始”设置是 *`current day minus 14 days`*。

* “结束”设置是 *`current day minus 7 days`*。

这个日期范围可作为一个组件拖至任何自由格式表中。
