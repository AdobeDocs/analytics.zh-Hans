---
title: 分类设置合并管理器
description: 将一个或多个分类集合并到单个分类集中。
exl-id: 032e93f6-9c11-4522-a02e-376eb4fd98bf
feature: Classifications
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# 分类集合并管理器

如果您有多个包含相似数据的分类集，则可以将它们合并到单个分类集中。 合并两个或多个分类集时，Adobe会生成一个新的分类集，其中包含来自每个单独分类集的所有分类数据。 如果您将数据上传到多个报告包或包含相同分类数据的维度，并且希望将它们合并到单个工作流中，合并会很有用。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]** > **[!UICONTROL 合并]**

运行合并后，将删除原始分类集，合并的分类集将取代原始分类集。 单击 **[!UICONTROL 添加]** 到 [创建整合](process.md).

## 筛选分类集

分类集合并管理器的左侧提供筛选条件设置以定位所需的合并。 单击过滤器图标可切换过滤器设置的可见性。 您可以通过以下方式筛选合并 **[!UICONTROL 状态]**， **[!UICONTROL 完成时间]**，或 **[!UICONTROL 创建时间]**.

![分类集合并筛选器](../../assets/classification-set-consolidation-filters.png)

分类集合并管理器列上方提供了其他筛选选项：

* **[!UICONTROL 按标题搜索]**：按名称搜索合并。
* **显示/隐藏列**：切换任意列的可见性，不包括 [!UICONTROL 名称].

## 分类集合并管理器列

分类集合并管理器中有以下列：

* **[!UICONTROL 名称]**：合并的名称。
* **[!UICONTROL 当前作业]**：当前作业。 <!-- todo: better description -->
* **[!UICONTROL 状态]**：合并的状态。 <!-- todo: get list of possible statuses -->
* **[!UICONTROL 创建日期]**：创建合并的日期和时间。
* **[!UICONTROL 完成日期]**：合并完成（或失败）的日期和时间。
