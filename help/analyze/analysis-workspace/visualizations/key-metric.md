---
description: 使用关键量度摘要可视化图表来比较两条时间线的量度表现。
title: 关键量度摘要
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 56%

---

# 关键量度摘要 {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="关键量度摘要"
>abstract="创建由线条、摘要变化和摘要数字图表组合而成的可视化效果。使用此可视化效果来比较两个时段内重要量度的趋势。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*本文记录了&#x200B;**Adobe Analytics**中的关键指标摘要可视化。<br/>查看本文的&#x200B;**Customer Journey Analytics**版本的[关键量度摘要](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric)。*

>[!ENDSHADEBOX]

[!UICONTROL 关键量度摘要]可视化让您看到重要量度在单个时间范围内的趋势。 它还允许您在两个时间范围内比较量度表现。 它还具备将多个可视化图表组合为一个可视化图表的优点：

* 显示主要日期范围和比较日期范围的量度趋势的&#x200B;**[!UICONTROL 行]**&#x200B;可视化图表

* **[!UICONTROL 摘要百分比变化]**&#x200B;显示主要日期范围和比较日期范围之间的量度增加或减少

* 度量的当前总值（[!UICONTROL **摘要编号**]）

## 用例

此可视化图表处理各种常见用例，包括：

* 一位分析师试图了解与去年同期相比，本月机会创造情况。

* 一位营销人员正在探索特定商机类型的商机开发从本月到上个月的变化。

* 一位高管想了解新预订从本季度到上季度的变化。

## 配置关键量度摘要

1. 将&#x200B;**[!UICONTROL 关键度量摘要]**&#x200B;可视化图表从左栏中的&#x200B;**[!UICONTROL 可视化图表]**&#x200B;菜单拖动到面板中。

   ![](assets/key-metric-config.png)

1. 使用以下选项配置可视化图表：

   | 配置设置 | 定义 |
   | --- | --- |
   | **[!UICONTROL 量度]** | 选择您希望检查的量度。 支持全部量度。 |
   | **[!UICONTROL 主要日期范围]** | 自由表格的当前日期范围。<p>从报表包中的任何可用日期范围中进行选择。</p> <p>如果要使用在可视化图表所在的面板上使用的相同日期范围，请选择&#x200B;[!UICONTROL **面板日期范围**]。</p> |
   | **[!UICONTROL 比较日期范围。]** | 要与主要日期范围进行比较的日期范围。 |
   | **[!UICONTROL 区段（可选）]** | 您对此摘要感兴趣的任何区段。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >当&#x200B;[!UICONTROL **主日期范围**]&#x200B;字段设置为&#x200B;[!UICONTROL **面板日期范围**]&#x200B;时，**[!UICONTROL 比较日期范围]**&#x200B;将自动更新，具体取决于您选择的&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;选项是相对于主日期范围还是固定的。
   >
   >* **相对：**&#x200B;如果将&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;字段设置为与主日期范围相关的选项（如&#x200B;[!UICONTROL **前一天**]、[!UICONTROL **上周同日**]、[!UICONTROL **前第4周同日**]&#x200B;等），则对&#x200B;[!UICONTROL **主日期范围**]&#x200B;字段的任何更新都会导致&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;自动更新为紧跟面板日期范围的时段。
   >* **固定：**&#x200B;如果&#x200B;[!UICONTROL **比较日期范围**]&#x200B;字段设置为固定日期范围（如&#x200B;**2023年2月3日**），则对&#x200B;[!UICONTROL **主要日期范围**]&#x200B;字段或面板日期范围所做的更改不会对&#x200B;[!UICONTROL **比较日期范围**]&#x200B;产生影响。 但是，对面板日期范围的任何更新都会导致&#x200B;[!UICONTROL **主日期范围**]&#x200B;自动更新。

1. 选择&#x200B;**[!UICONTROL 生成]**。

## 查看输出

输出应如下所示：

![](assets/key-metric-output.png)

查看输出时，请考虑以下事项：

* **[!UICONTROL 上一时段]**&#x200B;折线图（始终以灰色显示）对应于配置步骤中的&#x200B;**[!UICONTROL 比较日期范围]**。

* 如果在配置期间未指定比较日期范围，或在可视化图表设置中隐藏比较日期范围时，则仅显示主日期范围的线形图。摘要更改已隐藏。

* 从此处，您可以将鼠标悬停在线形图上，查看各个日期的统计数据：

![](assets/key-metric-output2.png)

## 可视化设置

关键量度摘要提供了多种灵活的设置，以便更好地报告和沟通重要量度。 可以通过可视化图表右上角的齿轮图标访问设置。

![](assets/key-metric-settings.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 强调百分比变化]** | 在可视化图表中心以突出的粗体显示摘要更改 |
| **[!UICONTROL 强调数值]** | 在可视化图表中心以突出的粗体显示摘要编号 |
| **[!UICONTROL 图例可见]** | 显示或隐藏可视化图表底部的图例 |
| **[!UICONTROL 显示注释]** | 显示或隐藏管理员添加的注释 |
| **[!UICONTROL 显示迷你图]** | 在图表底部显示或隐藏线形图。 隐藏时，图例将更改为不再在视觉上引用线条 |
| **[!UICONTROL 在迷你图上显示最小值和最大值]** | 在主线形图和比较线形图上显示或隐藏最小值和最大值 |
| **[!UICONTROL 显示比较]** | 显示或隐藏比较数据。 隐藏时，比较线形图和汇总更改对象将从视图中隐藏。 |
| **[!UICONTROL 显示总数]** | 显示或隐藏摘要编号 |
| **[!UICONTROL 显示原始差异]** | 显示或隐藏主要日期范围和次要日期范围中量度的总值之间的原始差异 |
| **[!UICONTROL 缩写值]** | 缩写数值以简化交流的见解（例如，20,000 -> 20K） |

## 编辑可视化图表

构建可视化图表后，您仍然可以编辑原始配置。

1. 单击可视化右上角的铅笔图标（设置齿轮图标旁边）。

   ![](assets/edit-icon.png)

   现在，您将返回到原始配置视图。

1. 根据需要更改量度、主要日期范围、比较日期范围或区段。
