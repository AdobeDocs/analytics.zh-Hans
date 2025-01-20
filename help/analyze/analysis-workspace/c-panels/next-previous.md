---
description: 显示特定维度的下一个或上一个维度项的面板。
title: “下一项或上一项”面板
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 36%

---

# “下一项或上一项”面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="下一项或上一项"
>abstract="创建一个面板来了解人们来自的前一个维度或人们要去的下一个维度。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="下一项或上一项"
>abstract="分析访客之前最常来自何处或后续最常访问的地方是什么。<br/><br/>**维度**：选择一个维度。例如&#x200B;**页面**。<br/>**维度项**：选择具体的维度项目。例如&#x200B;**主页**。<br/>**方向**：选择&#x200B;**下一项**&#x200B;以查看所选维度项目后的下一个维度项目。选择&#x200B;**上一项**&#x200B;来查看您所选的维度项目之前的维度项目。<br/>**容器**：选择&#x200B;**线程**&#x200B;来查看同一线程中的下一个/上一个维度项目，或选择&#x200B;**人员**&#x200B;来查看同一个人的上一个/下一个维度项目。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的下一个或上一个项目面板。_<br/>_查看本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[下一个或上一个项目面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous)。_

>[!ENDSHADEBOX]

**[!UICONTROL 下一个或上一个项目]**&#x200B;面板包含许多表和可视化图表，用于标识特定维度的下一个或上一个维度项目。 例如，您可能希望探索客户在访问主页后最常访问哪些页面。

## 使用

要使用&#x200B;**[!UICONTROL 下一个或上一个项目]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 下一个或上一个项目]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入

您可以使用以下输入设置配置[!UICONTROL 下一个或上一个项]面板：

![下一个或上一个项目面板](assets/next-or-previous-item.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 维度]** | 选择要为其浏览下一个或上一个项目的维度。 |
| **[!UICONTROL 维度项]** | 在下次/上一次查询的中心选择特定维度项目。 |
| **[!UICONTROL 方向]** | 指定您要查找[!UICONTROL Next]还是[!UICONTROL Previous]维度项。 |
| **[!UICONTROL 容器]** | 选择容器[!UICONTROL 会话]或[!UICONTROL 人员]（默认值），以确定查询的范围。 |

{style="table-layout:auto"}

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出

[!UICONTROL 下一个或上一个项目]面板返回一组丰富的数据和可视化图表，以帮助您更好地了解特定维度项目之后或之前的具体情况。


![下一个/上一个面板输出](assets/next-or-previous-item-output.png)


| 可视化图表 | 描述 |
| --- | --- |
| **[!UICONTROL 水平条]** | 根据您选择的维度项目列出下一个（或上一个）项目。 将鼠标悬停在单个栏上会突出显示自由格式表中的相应项目。 |
| **[!UICONTROL 摘要数字]** | 当月（到目前为止）所有下一个或上一个维度项目发生次数的高级摘要编号。 |
| **[!UICONTROL 自由格式表]** | 以表格式根据所选的维度项列出下一个（或上一个）项目。 例如，在主页或Workspace页面之后（或之前），哪些（按发生次数）是用户访问的最受欢迎页面。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Create a panel](/help//analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Next or previous item panel

This panel contains a number of tables and visualizations to easily identify the next or previous dimension item for a specific dimension. For example, you might want to explore which pages customers went to most often after they visited the Home page.

## Access the panel

You can access the panel from within [!UICONTROL Reports] or within [!UICONTROL Workspace].

| Access point | Description |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>The panel is already dropped into a project.</li><li>The left rail is collapsed.</li><li>If you selected [!UICONTROL Next page], default settings have already been applied, such as [!UICONTROL Page] for [!UICONTROL Dimension], and the top page as the [!UICONTROL Dimension Item], [!UICONTROL Next] for [!UICONTROL Direction] and [!UICONTROL Visit] for [!UICONTROL Container]. You can modify all these settings.</li></ul>![Next/Previous panel](assets/next-previous.png)|
| Workspace | Create a new project and select the Panel icon in the left rail. Then drag the [!UICONTROL Next or previous item] panel above the Freeform table. Notice that the [!UICONTROL Dimension] and [!UICONTROL Dimension Item] fields are left blank. Select a dimension from the drop-down list. [!UICONTROL Dimension items] are populated based on the [!UICONTROL dimension] you chose. The top dimension item gets added, but you can select a different item. The defaults are Next and Visitor. Again, you can modify these as well.<p>![Next/Previous panel](assets/next-previous2.png) |

{style="table-layout:auto"}

## Panel Inputs {#Input}

You can configure the [!UICONTROL Next or previous item] panel panel using these input settings:

| Setting | Description |
| --- | --- |
| Segment (or other component) drop zone | You can drag and drop segments or other components to further filter your panel results. |
| Dimension | The dimension for which you want to explore next or previous items. |
| Dimension Item | The specific item at the center of your next/previous inquiry. |
| Direction | Specify whether you are looking for the [!UICONTROL Next] or the [!UICONTROL Previous] dimension item. |
| Container | [!UICONTROL Visit] or [!UICONTROL Visitor] (default) determine the scope of your inquiry. |

{style="table-layout:auto"}

Click **[!UICONTROL Build]** to build the panel.

## Panel output {#output}

The [!UICONTROL Next or previous item] panel returns a rich set of data and visualizations to help you better understand what occurrences follow or precede specific dimension items.

![Next/Previous panel output](assets/next-previous-output.png)

![Next/Previous panel output](assets/next-previous-output2.png)

| Visualization | Description |
| --- | --- |
| Horizontal bar | Lists the next (or previous) items based on the dimension item you chose. Hovering over an individual bar highlights the corresponding item in the Freeform table. |
| Summary number | High-level summary number of all next or previous dimension item occurrences for the current month (so far.) |
| Freeform table | Lists the next (or previous) items based on the dimension item you chose, in a table format. For example, which were the most popular pages (by occurrences) that people went to after (or before) the home page or the workspace page. |

{style="table-layout:auto"}

-->