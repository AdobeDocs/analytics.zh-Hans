---
title: 分类设置合并管理器
description: 将一个或多个分类集合并到单个分类集中。
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# 分类集合并管理器

如果您有多个分类集包含相似数据，则可以将它们合并到单个分类集中。 合并两个或多个分类集时，Adobe会生成一个新的分类集，其中包含来自每个单独分类集的所有分类数据。 当您将数据上传到多个报表包或维度且这些报表包或维度包含相同的分类数据并希望将它们合并到单个工作流中时，合并很有用。 您必须具有Adobe Analytics的产品管理员访问权限才能查看分类集合并管理器。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]** > **[!UICONTROL 合并]**

运行合并后，将删除原始分类集，合并的分类集将替换它们。 单击&#x200B;**[!UICONTROL 添加]**&#x200B;到[创建合并](process.md)。

## 筛选分类集

分类集合并管理器的左侧提供筛选条件设置以定位所需的合并。 单击过滤器图标可切换过滤器设置的可见性。 您可以按&#x200B;**[!UICONTROL 状态]**、**[!UICONTROL 完成时间]**&#x200B;或&#x200B;**[!UICONTROL 创建时间]**&#x200B;筛选合并。

![分类集合并筛选器](../../assets/classification-set-consolidation-filters.png)

分类集合并管理器列上方提供了其他筛选器选项：

* **[!UICONTROL 按标题搜索]**：按名称搜索合并。
* **显示/隐藏列**：切换除[!UICONTROL 名称]之外的任何列的可见性。

## 分类集合并管理器列

分类集合并管理器中有以下列：

* **[!UICONTROL 名称]**：合并的名称。
* **[!UICONTROL 当前作业]**：当前作业。<!-- todo: better description -->
* **[!UICONTROL 状态]**：合并的状态。<!-- todo: get list of possible statuses -->
* **[!UICONTROL 创建日期]**：合并的创建日期和时间。
* **[!UICONTROL 完成日期]**：合并完成（或失败）的日期和时间。
