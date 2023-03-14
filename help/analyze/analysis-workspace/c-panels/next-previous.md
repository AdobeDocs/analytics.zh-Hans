---
description: 显示特定维度的下一个或上一个维度项目的面板。
title: 下一个或上一个项目面板
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: c289f4aa1e49e428182fed9a871a1f90dd1f5c42
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# 下一个或上一个项目面板

此 [!UICONTROL 下一个或上一个项目] 面板开始于Reports &amp; Analytics中的报告，位于 [!UICONTROL 报告] > [!UICONTROL 最受欢迎] > [!UICONTROL 下一页/上一页]. 它现在也是一个Workspace面板。 此面板包含许多表和可视化图表，用于轻松识别特定维度的下一个或上一个维度项。 例如，您可能想要探索客户在访问主页后最常访问哪些页面。

## 访问面板

您可以从中访问面板 [!UICONTROL 报告] 或范围 [!UICONTROL 工作区].

| 接入点 | 描述 |
| --- | --- |
| [!UICONTROL 报告] | <ul><li>该面板已拖放到项目中。</li><li>左侧边栏处于折叠状态。</li><li>如果您已选择 [!UICONTROL 下一页]，已应用默认设置，例如 [!UICONTROL 页面] 对象 [!UICONTROL Dimension]，并且顶部页面为 [!UICONTROL Dimension项目]， [!UICONTROL 下一个] 对象 [!UICONTROL 方向] 和 [!UICONTROL 访问] 对象 [!UICONTROL 容器]. 您可以修改所有这些设置。</li></ul>![下一个/上一个面板](assets/next-previous.png) |
| 工作区 | 创建新项目并选择左边栏中的面板图标。 然后拖动 [!UICONTROL 下一个或上一个项目] 自由格式表上方的面板。 请注意 [!UICONTROL Dimension] 和 [!UICONTROL Dimension项目] 字段留空。 从下拉列表中选择一个维度。 [!UICONTROL Dimension项目] 填充基于 [!UICONTROL 维度] 你选择了。 将添加排名最前的维度项目，但您可以选择其他项目。 默认为Next和Visitor。 同样，您也可以修改这些内容。<p>![下一个/上一个面板](assets/next-previous2.png) |

{style="table-layout:auto"}

## 面板输入 {#Input}

您可以配置 [!UICONTROL 下一个或上一个项目] 使用这些输入设置的面板面板：

| 设置 | 描述 |
| --- | --- |
| 区段（或其他组件）拖放区域 | 您可以拖放区段或其他组件以进一步筛选面板结果。 |
| 维度 | 要浏览下一个或上一个项目的维度。 |
| Dimension项目 | 您下次/上次查询中心的特定项目。 |
| 方向 | 指定您是否正在查找 [!UICONTROL 下一个] 或 [!UICONTROL 上一个] 维度项目。 |
| 容器 | [!UICONTROL 访问] 或 [!UICONTROL 访客] （默认）确定查询范围。 |

{style="table-layout:auto"}

单击 **[!UICONTROL 生成]** 以构建面板。

## 面板输出 {#output}

此 [!UICONTROL 下一个或上一个项目] 面板可返回一组丰富的数据和可视化图表，以帮助您更好地了解特定维度项目之后或之前的匹配项。

![下一个/上一个面板输出](assets/next-previous-output.png)

![下一个/上一个面板输出](assets/next-previous-output2.png)

| 可视化图表 | 描述 |
| --- | --- |
| 水平条 | 根据您选择的维度项目列出下一个（或上一个）项目。 将鼠标悬停在单个栏上会突出显示自由格式表中的相应项目。 |
| 摘要数字 | 当月（到目前为止）所有下一个或上一个维度项目发生次数的高级摘要编号。 |
| 自由格式表 | 以表格式根据您选择的维度项列出下一个（或上一个）项目。 例如，在主页或Workspace页面之后（或之前），哪些页面是用户访问的最受欢迎页面（按发生次数）。 |

{style="table-layout:auto"}
