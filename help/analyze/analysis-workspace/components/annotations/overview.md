---
title: 注释概述
description: 如何在工作区中使用注释。
role: User, Admin
solution: Analytics
exl-id: 722d7636-f619-479a-97f1-3da23e8f7f83
source-git-commit: 38170806d0fbf6ae373ae089872f8d25306f416e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 13%

---

# 注释概述

>[!NOTE]
>
>此功能当前正在进行小范围测试。

注释使您能够有效地将上下文数据的细微差别和见解传达给您的组织。它们允许您将日历事件与特定维度/量度关联。 您可以使用已知数据问题、公共假日、营销活动启动次数等对日期或日期范围添加批注。 然后，您可以通过图形显示事件，并查看促销活动或其他事件是否影响了网站流量、收入或任何其他量度。

例如，假设您正在与您的组织共享项目。 如果由于销售事件导致流量出现重大尖峰，则可以创建“促销活动启动日期”批注，并将其适用于整个报表包。 当用户查看包含该日期的任何数据集时，他们会在项目中看到注释及其数据。

![](assets/multi-day.png)

请牢记这一点：

* 批注可以绑定到单个日期或日期范围。

* 它们可以应用于整个数据集，或应用于指定的量度、维度或区段。

* 它们可以应用于创建它们的项目（默认）或所有项目。

* 它们可以应用于创建它们的报表包（默认）或所有报表包。

## 权限

默认情况下，只有管理员才能创建注释。 用户有权查看批注，这与他们与其他Analytics组件（如区段、计算量度等）一样。

但是，管理员可以为 [!UICONTROL 注释创建] 权限（Analytics工具） [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=en).

## 启用或禁用注释

可以在以下几个级别打开或关闭注释：

* 在可视化级别： [!UICONTROL 可视化图表] 设置> [!UICONTROL 显示注释]

* 在项目级别： [!UICONTROL 项目信息和设置] > [!UICONTROL 显示注释]

* 在用户级别： [!UICONTROL 组件] > [!UICONTROL 用户首选项] > [!UICONTROL 数据] > [!UICONTROL 显示注释]

![](assets/show-ann.png)

![](assets/show-ann2.png)
