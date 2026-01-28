---
title: 管理分类集合并
description: 了解如何将一个或多个分类集合并到单个分类集中。
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 3%

---

# 管理分类合并

如果您有多个包含相似分类数据的分类集，则可以将它们合并到单个分类集中。 合并两个或多个分类集时，Adobe会生成一个新的分类集，其中包含来自每个单独分类集的所有分类数据。 当您将数据上传到多个报表包时，合并会很有用。 或者，当您具有包含相同分类数据并希望将它们合并到单个工作流中的维度时。

您必须具有Adobe Analytics的产品管理员访问权限才能查看分类集合并管理器。



要管理分类合并，请执行以下操作：

1. 从Adobe Analytics顶部菜单栏中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 分类集]**。
1. 在&#x200B;**[!UICONTROL 分类集]**&#x200B;中，选择&#x200B;**[!UICONTROL 合并]**&#x200B;选项卡。


## 分类合并管理器

**[!UICONTROL 分类集 — 合并]**&#x200B;管理器具有以下接口元素：

![分类集 — 合并管理器](assets/classifications-sets-consolidations.png)



### 分类合并列表

列表➊显示已创建和验证的、可能正在合并的分类合并。 该列表具有以下各列：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 合并名称]** | 分类集合并的名称。 |
| **[!UICONTROL 当前作业]** | 与分类集合并关联的作业。 |
| **[!UICONTROL 状态]** | 分类集合并的状态。 可能的值包括： **[!UICONTROL 已创建]**、**[!UICONTROL 已取消]**、**[!UICONTROL 正在取消]**、**[!UICONTROL 正在验证]**、**[!UICONTROL 失败验证]**、**[!UICONTROL 已验证]**、**[!UICONTROL 比较]**、**[!UICONTROL 比较失败]**、**[!UICONTROL 合并]**、**[!UICONTROL 已提交]**、**[!UICONTROL 合并]**、**[!UICONTROL 合并失败]**、**[!UICONTROL 合并失败已成功]**、**[!UICONTROL 正在等待审批]**、**[!UICONTROL 正在完成]**、**[!UICONTROL 失败]**&#x200B;或&#x200B;**[!UICONTROL 已完成]**。 |
| **[!UICONTROL 创建时间]** | 分类集合并的创建时间。 |
| **[!UICONTROL 完成时间]** | 分类合并的完成时间。 |


要调整分类合并列表中的列的大小，您可以：

* 将鼠标悬停在列分隔符上，并将列分隔符拖至所需的列宽。
* 选择![ChevronDown](/help/assets/icons/ChevronDown.svg)并选择&#x200B;**[!UICONTROL 调整列大小]**。 带有调整大小按钮的垂直线允许您使用将列大小调整到所需的大小。

对分类合并列表中的列进行排序

* 选择![V形向下](/help/assets/icons/ChevronDown.svg)并选择&#x200B;**[!UICONTROL 升序排序]**&#x200B;或&#x200B;**[!UICONTROL 降序排序]**。 箭头(↑↓)指示哪一列以及该列的排序方式。

### 搜索和按钮

在分类合并列表顶部的➋区域中，您可以：

* 搜索![搜索](/help/assets/icons/Search.svg)以查找分类合并。 结果将显示在分类合并列表中。 选择![CrossSize200](/help/assets/icons/CrossSize200.svg)以清除搜索。
* 删除应用于分类集合并列表的任何筛选器。 选择![CrossSize100](/help/assets/icons/CrossSize100.svg)以删除筛选器。
* 创建新的分类集合并。 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**&#x200B;以打开分类集合并对话框并定义新的分类集合并。
* 定义分类合并列表的列。 选择![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然后在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中，选择要在&#x200B;**[!UICONTROL 下显示的列。选择要显示的列]**。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用列设置。


### 操作栏

在分类集列表中选择一个或多个分类集时，将显示一个蓝色操作栏➌。 操作栏中提供了以下操作：

| 图标 | 操作 | 描述 |
|---|---|---|
| ![编辑](/help/assets/icons/Edit.svg) | **[!UICONTROL 编辑]** | [编辑分类集合并](process.md#edit-a-consolidation) |
| ![视图详细信息](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL 查看]** | 查看分类集合并的详细信息。 根据状态，您可以[批准](process.md#approve)或[取消](process.md#cancel)合并。 |


### 过滤器面板

选择![筛选器](/help/assets/icons/Filter.svg)以显示筛选器面板➍，该面板允许您筛选分类合并列表。 您可以按以下项过滤：

* **[!UICONTROL 状态]**。 选择一个可能值以筛选有关状态的分类合并列表。 |
* **[!UICONTROL 完成时间]**。 选择其中一个可能值以在完成时筛选分类合并列表。
* **[!UICONTROL 创建时间]**。 选择其中一个可能值以在完成时筛选分类合并列表。


选择![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏筛选器]**&#x200B;以隐藏筛选器面板。

请注意，“过滤器”面板中显示的过滤器反映了预加载的分类合并的选项。
