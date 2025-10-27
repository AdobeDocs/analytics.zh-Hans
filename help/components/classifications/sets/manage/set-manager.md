---
title: 管理分类集
description: 在Adobe Analytics中管理分类集。
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---

# 管理分类集

您可以在“分类集”管理界面中创建、重命名、编辑、合并、删除和标记分类集。 您还可以过滤和搜索特定分类集。

要管理分类集，请执行以下操作：

1. 从Adobe Analytics顶部菜单栏中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 分类集]**。
1. 在&#x200B;**[!UICONTROL 分类集]**&#x200B;中，选择&#x200B;**[!UICONTROL 分类集]**&#x200B;选项卡。

## 分类集管理器

**[!UICONTROL 分类集]**&#x200B;管理器具有以下接口元素：

![分类集管理器](assets/classification-sets-manage.png)


### 分类集列表

**[!UICONTROL 分类集]**&#x200B;列表➊显示所有分类集。 该列表具有以下各列：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 分类集]** | 分类集的标题。 选择标题以[编辑分类集](create.md#edit-a-classification-set)。 |
| **[!UICONTROL 订阅]** | 分类集应用的订阅数。 |
| **[!UICONTROL 分类]** | 分类集包含的分类维度数。 |
| **[!UICONTROL 自动]** | 分类集是否配置为自动从云位置导入数据？ 此自动化可以配置为[分类集架构](schema.md)的一部分。 |
| **[!UICONTROL 上次修改时间]** | 分类集的上次修改的时间戳。 |

要调整分类集列表中的列大小，您可以：

* 将鼠标悬停在列分隔符上，并将列分隔符拖至所需的列宽。
* 选择![ChevronDown](/help/assets/icons/ChevronDown.svg)并选择&#x200B;**[!UICONTROL 调整列大小]**。 带有调整大小按钮的垂直线允许您使用将列大小调整到所需的大小。

对分类集列表中的列进行排序

* 选择![V形向下](/help/assets/icons/ChevronDown.svg)并选择&#x200B;**[!UICONTROL 升序排序]**&#x200B;或&#x200B;**[!UICONTROL 降序排序]**。 箭头(↑↓)指示哪一列以及该列的排序方式。

### 搜索和按钮

在分类集列表顶部的➋区域中，您可以：

* 搜索![搜索](/help/assets/icons/Search.svg)以查找分类集。 结果将显示在分类集列表中。 选择![CrossSize200](/help/assets/icons/CrossSize200.svg)以清除搜索。
* 删除应用于分类集列表的任何过滤器。 选择![CrossSize100](/help/assets/icons/CrossSize100.svg)以删除筛选器。
* 选择![MoreCircle](/help/assets/icons/MoreCircle.svg)以加载附加1000个分类集。 最初，分类集列表最多显示1000个分类集。
* 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新建]**&#x200B;以[创建新的分类集](create.md#create-a-classification-set)。
* 定义分类集列表的列。 选择![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然后在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中，选择要在&#x200B;**[!UICONTROL 下显示的列。选择要显示的列]**。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用列设置。


### 操作栏

在分类集列表中选择一个或多个分类集时，将显示一个蓝色操作栏➌。 操作栏中提供了以下操作：

| 图标 | 操作 | 描述 |
|---|---|---|
| ![编辑](/help/assets/icons/Edit.svg) | **[!UICONTROL Edit]** | [在分类集生成器中编辑分类集](create.md#edit-a-classification-set)。 |
| ![重命名](/help/assets/icons/Rename.svg) | **[!UICONTROL 重命名]** | 重命名分类集。<br/>在&#x200B;**[!UICONTROL 重命名：_分类集_]**&#x200B;对话框中，输入新名称并选择&#x200B;**[!UICONTROL 重命名]**。 |
| ![Merge](/help/assets/icons/Merge.svg) | **[!UICONTROL 合并]** | [合并分类集](/help/components/classifications/sets/consolidations/manage.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除分类集。<br/> **[!UICONTROL 删除&#x200B;_分类集_？]**&#x200B;对话框出现。 无法撤消删除分类集。 任何使用此分类集的计划项目或合并将继续使用此分类集的定义，直至您重新保存计划项目或重新验证计划合并。 选择&#x200B;**[!UICONTROL 删除]**&#x200B;以删除分类集。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 标记]** | 标记分类集。<br/>在&#x200B;**[!UICONTROL 标记：_分类集_]**&#x200B;对话框中，从&#x200B;**[!UICONTROL 标记]**&#x200B;下拉菜单中选择一个或多个标记以添加标记。 或者输入一个或多个新标记。 使用![CrossSize100](/help/assets/icons/CrossSize100.svg)删除标记。 <br/>选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存标记。 |


### 过滤器面板

选择![筛选器](/help/assets/icons/Filter.svg)以显示用于筛选分类集列表的筛选器面板➍。 您可以按以下项过滤：

* **[!UICONTROL 标记]**。选择一个或多个标记以筛选标记上的分类集列表。
* **[!UICONTROL 报告包]**。 选择一个或多个报告包以筛选报告包上的分类集列表。

选择![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏筛选器]**&#x200B;以隐藏筛选器面板。

请注意，“过滤器”面板中显示的过滤器反映了预加载的分类集的选项。


<!-- old content

The Classification set manager allows you to create, edit, or delete classification sets.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Classification sets consist of **Subscriptions** (report suite and dimension combinations) and **Classification names** (dimensions containing classification data). Subscriptions are configured under [Settings](settings.md), while classification names are configured under [Schema](schema.md).

## Filter classification sets

The left side of the Classification set manager provides filter settings to locate the desired classification set. Clicking the filter icon toggles the filter settings visibility. You can filter classification sets by **[!UICONTROL Tags]** or **[!UICONTROL Report suite]**.

![Classification set filters](../../assets/classification-set-filters.png)

Note that 1,000 classification sets are preloaded at a time. The filters shown in the left rail reflect the options for the sets that are preloaded.

## Classification set manager columns

The following columns are available in the Classification set manager:

* **[!UICONTROL Classification set]**: The classification set name. Clicking a classification set name edits its [settings](settings.md).
* **[!UICONTROL Subscriptions]**: The number of subscriptions that this classification set applies to.
* **[!UICONTROL Classifications]**: The number of classification dimensions that the classification set contains.
* **[!UICONTROL Automated]**: Determines if the classification set is configured to automatically import data from a cloud location. Automation can be configured in the classification set's [schema](schema.md).
* **[!UICONTROL Last Modified]**: The date and time that the classification set was last modified.

## Create or edit options

The following buttons are available in the Classification set manager:

* **[!UICONTROL Add]**: [Create](create.md) a classification set.
* **[!UICONTROL Search by title]**: Search for classification sets by name.
* **[!UICONTROL Load more]**: The Classification set manager initially displays up to 1000 classification sets. This button loads 1000 more classification sets.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Classification set].

Select one or more classification sets by clicking the checkbox next to the desired classification set. Selecting a classification set reveals the following options:

* **[!UICONTROL Tag]**: Add one or more tags to the selected classification sets, which allows you to organize or group classification sets to make them easier to locate in the future.
* **[!UICONTROL Delete]**: Deletes the classification set. Classification dimensions based on this classification set are no longer available. Scheduled projects using the deleted classification set continue using dependent dimensions until you resave the scheduled project.
* **[!UICONTROL Consolidate]**: Start a new [consolidation](../consolidations/process.md).
* **[!UICONTROL Rename]**: Rename the selected classification set.

-->