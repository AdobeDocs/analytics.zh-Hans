---
description: 了解如何在 Analysis Workspace 中使用和管理项目。使用项目管理器可对项目进行创建、删除、移动、共享、审批、固定、复制和添加标记等管理操作。
keywords: Analysis Workspace
title: 项目概述
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1680'
ht-degree: 91%

---

# 项目概述

通过 Workspace 项目，可将面板、可视化图表和组件组合起来，以得出您的分析结果，并与您组织中的任何人共享。在开始您的第一个项目之前，请了解如何访问、浏览和管理您的项目。

要访问Adobe Analytics中的项目，请选择&#x200B;**[!UICONTROL Workspace]**。  **[!UICONTROL 项目]**&#x200B;管理器列出了您拥有的所有项目或与您共享的项目。具有项目列表的项目管理器也是Adobe Analytics的默认登录页面，除非您已在首选项中进行其他配置。

![显示项目列表的项目登陆页面。](assets/projects.png)


## 标题区

在标题区域 ➊ 内，您可以创建一个项目，创建一个文件夹，编辑您的偏好设置以及显示或隐藏带有附加图块的面板。

* 要显示或隐藏左侧面板，以便您在&#x200B;**[!UICONTROL 项目]**&#x200B;和&#x200B;**[!UICONTROL 学习]**&#x200B;之间进行选择，请选择![边栏](/help/assets/icons/Rail.svg)。
* 标题会显示“项目”，并可选择性地带有您所选文件夹的路径。例如[!UICONTROL 项目] > **[!UICONTROL 公司文件夹]**。您可以选择单个子文件夹部分，以直接跳转到特定文件夹。
* 要显示[**[!UICONTROL 空白项目]**](create-projects.md)、[**[!UICONTROL 空白移动记分卡]**](/help/analyze/mobile-app/create-scorecard.md)、**[!UICONTROL 打开文档]**&#x200B;和&#x200B;**[!UICONTROL 打开发行说明]**&#x200B;的磁贴，请选择![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 显示更多]**。 要隐藏带有图块的区域，请选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 显示更少]**。
* 根据您使用[显示选择器](#show-selector)选择要显示的内容，您可以编辑偏好设置，并对&#x200B;**[!UICONTROL 项目]**&#x200B;中当前可见的文件夹执行操作：

  | 操作 | 描述 |
  |---|---|
  | **[!UICONTROL 创建项目]** | 选择以[创建新项目](create-projects.md)。 |
  | **[!UICONTROL 创建文件夹]** | 选择以[创建新文件夹](workspace-folders/create-folders.md)。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 编辑偏好设置]** | 为所有项目[编辑偏好设置](/help/analyze/analysis-workspace/user-preferences.md)。当痕迹导航导致空间有限时，此操作会作为![更多](/help/assets/icons/More.svg)子菜单的一部分。 |
  | **[!UICONTROL 添加项目]** | 选择以在当前文件夹中[添加项目](workspace-folders/add-projects.md)。当痕迹导航导致空间有限时，此操作会作为![更多](/help/assets/icons/More.svg)子菜单的一部分。 |
  | **[!UICONTROL 重命名文件夹]** | [重命名](workspace-folders/manage-folders.md#rename-folders)当前文件夹。 |
  | **[!UICONTROL 移动文件夹]** | [移动](workspace-folders/manage-folders.md#move-folders)当前文件夹。 |
  | **[!UICONTROL 删除文件夹]** | [删除](workspace-folders/manage-folders.md#delete-folders)当前文件夹。 |




## 项目列表


项目列表 ➋ 显示您拥有的所有项目，以及与您共享的所有项目。该列表具有以下各列：

| 列 | 描述 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 当选择一个或多个项目时，项目界面底部会出现一个蓝色的操作栏。有关更多详细信息，请参阅[操作](#actions)。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择以加入收藏 ![Star](/help/assets/icons/Star.svg) 或取消收藏 ![StarOutline](/help/assets/icons/StarOutline.svg) 一个项目。 |
| **[!UICONTROL 标题和描述]** | 要编辑项目，请选择标题链接，这会打开[工作区项目](/help/analyze/analysis-workspace/home.md)。与您共享的项目会以 ![分享](/help/assets/icons/ShareAlt.svg) 标示。选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 以显示一个弹出菜单，其中包含有关该项目的更多详细信息。选择![更多](/help/assets/icons/More.svg)以打开带有操作选项的上下文菜单。有关更多详细信息，请参阅[操作](#actions)。 |
| **[!UICONTROL Type]** | 工作区项目，![FolderUser](/help/assets/icons/FolderUser.svg) 文件夹，或者[移动记分卡](/help/analyze/mobile-app/home.md)。 |
| **[!UICONTROL 标记]** | 应用于项目的标记。 |
| **[!UICONTROL 已计划]** | 是否计划通过电子邮件将项目发送给收件人。相关选项包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 开启]**&#x200B;或者 ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 关闭]**。请参阅[向其他人发送项目数据](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)。 |
| **[!UICONTROL 共享链接（任何人）]** | 是否与任何人共享项目，包括无权访问 Analysis Workspace 的人员。相关选项包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 有效]**&#x200B;或者 ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 无效]**。有关详细信息，请参阅[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)中的[与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)。 |
| **[!UICONTROL 项目角色]** | 您在项目中的角色。相关选项包括：编辑、复制、查看。有关更多信息，请参阅[项目角色](/help/analyze/analysis-workspace/curate-share/curate.md)。 |
| **[!UICONTROL 报告包]** | 与项目关联的报表包。 |
| **[!UICONTROL 所有者]** | 创建此项目的人员（您或与您共享此项目的人员）。 |
| **[!UICONTROL 共享对象]** | 已与其共享该项目的用户。 |
| **[!UICONTROL 上次修改时间]** | 项目上次修改的日期和时间。 |
| **[!UICONTROL 上次打开时间]** | 项目上次打开的日期和时间。 |
| **[!UICONTROL 组件 ID]** | 组件的ID。 |
| **[!UICONTROL 最长日期范围]** | 项目中任何面板或可视化图表的最长日期范围。 |
| **[!UICONTROL 查询次数]** | 项目中包含的查询总数。 |
| **[!UICONTROL 位置]** | 项目所在的文件夹。 |

将鼠标悬停在任意列标题上即可显示 ![ChevronDown](/help/assets/icons/ChevronDown.svg)，并从上下文菜单中选择：

* **[!UICONTROL 升序排序]**
* **[!UICONTROL 降序排序]**
* **[!UICONTROL 调整列大小]**。一条蓝线会显示，以帮助您调整列的大小。

### 操作

您可以使用上下文菜单![更多](/help/assets/icons/More.svg)或蓝色操作栏对一个或多个项目执行操作。

| 图标 | 操作 | 描述 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *已选择]** | 取消选择您选择的项目和文件夹，并移除蓝色操作栏。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除一个或多个项目或文件夹。系统将提示您确认。 <p>您要删除的项目：</p><ul><li>无法恢复</li><li>从项目列表中移除</li><li>无法再通过其 URL 访问</li><li>不再包含在计划交付中（如果之前已配置为计划交付）<br/>有关计划交付的信息，请参阅 [计划项目](/help/components/scheduled-projects-manager.md)。  </p> |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共享]** | 共享项目。请参阅[共享项目](/help/analyze/analysis-workspace/curate-share/share-projects.md)，以了解更多信息。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重命名]** | 重命名项目。打开&#x200B;**[!UICONTROL 重命名：*项目名称对话框&#x200B;*]**。输入新名称并选择**[!UICONTROL 保存&#x200B;]**。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 复制]** | 复制一个或多个项目。相关会获得相同的名称和后缀 `(Copy)`。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL 固定]**&#x200B;或者&#x200B;**[!UICONTROL 取消固定]** | 固定或取消固定一个或多个项目或文件夹。固定的项目和文件夹会在列表顶部显示，并忽略您指定的排序顺序。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 上移]** | 将固定的项目或文件夹在项目列表中上移。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 下移]** | 将固定的项目或文件夹在项目列表中下移。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 标记]** | 标记一个或多个项目或文件夹。**[!UICONTROL 标记组件]**&#x200B;对话框会显示，以选择一个或多个标记。选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存所选项目或文件夹的标记。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 批准]**&#x200B;或者&#x200B;**[!UICONTROL 拒绝]** | 批准或拒绝项目。只有管理员可以批准项目。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出 CSV]** | 将选定的项目导出到名为 `Project List.csv` 的 CSV 文件中。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL 添加项目]** | 将一个或多个项目添加到选定文件夹。在&#x200B;**[!UICONTROL 添加项目]**&#x200B;中，您可以选择一个或多个项目。选择&#x200B;**[!UICONTROL 添加]**，将这些项目添加到文件夹中。请参阅[在文件夹中添加项目](workspace-folders/add-projects.md#from-inside-a-folder)，以了解更多信息。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移动到]** | 将一个或多个选定的项目移动到文件夹。在&#x200B;**[!UICONTROL 选择文件夹]**&#x200B;中，选择要将选定项目移动到的文件夹，然后选择&#x200B;**[!UICONTROL 移动]**。请参阅[在文件夹中添加项目](workspace-folders/add-projects.md#from-the-project-list)，以了解更多信息。 |



## 显示选择器

您可以使用&#x200B;**[!UICONTROL 显示]**&#x200B;选择器 ➌ 来切换项目界面的外观。**[!UICONTROL 显示]**&#x200B;选择器定义了[标题区域](#title-area)中可用的选项，以及[项目列表](#project-list)中显示的列。

* 要更改[标题区域](#title-area)可用的选项，请选择&#x200B;**[!UICONTROL 显示]****[!UICONTROL 所有项目]**&#x200B;或&#x200B;**[!UICONTROL 显示]****[!UICONTROL 文件夹和项目]**。

* 要定义在[项目列表](#project-list)中显示哪些列，请选择 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然后从&#x200B;**[!UICONTROL 自定义表格]**&#x200B;对话框中选择或取消选择列。选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用自定义设置。有关列的更多详细信息，请参阅[项目列表](#project-list)。

## 过滤器面板

您可以使用过滤器面板 ➍ 过滤[项目列表](#project-list)中的项目和文件夹。要显示或隐藏过滤器面板，请使用![过滤器](/help/assets/icons/Filter.svg)。

过滤器面板由以下部分组成。

### 标记

| 标记 | 描述 |
|---|---|
| ![标记](assets/projects-filters-tags.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 标记]**&#x200B;部分按标记进行过滤。 <ul><li>您可以使用 ![搜索](/help/assets/icons/Search.svg) *搜索标记*&#x200B;来搜索您想要用于过滤的标记。</li><li>您可以选择多个标记。可用的标记取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**2︎⃣**：当前过滤器生成的项目可用的标记数量。</li><li>7︎⃣：与特定标记相关的项目数量。</li></ul></li></ul> |


### 报表包

| 报表包 | 描述 |
|---|---|
| ![报告包](assets/projects-filters-reportsuites.png){width="300"} | 通过&#x200B;**[!UICONTROL 报表包]**&#x200B;部分，可筛选报表包。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg) *搜索报表包*&#x200B;来搜索要用于过滤的报表包。</li><li>您可以选择多个报表包。 可用的报表包取决于在过滤器面板的其他部分中所做的选择。</li><li>这些数字表明：<ul><li>**3︎⃣**：由当前筛选器生成的项目可用的报表包数。</li><li>⃣4︎：与特定报表包关联的项目数。</li></ul></li></ul> |


### 所有者

| 所有者 | 描述 |
|---|---|
| ![所有者](assets/projects-filters-owners.png){width="300"} | **[!UICONTROL 所有者]**&#x200B;部分允许您过滤所有者。 <ul><li>您可以使用 ![搜索](/help/assets/icons/Search.svg) *搜索所有者*&#x200B;来搜索您想要用于过滤的所有者。</li><li>您可以选择多个所有者。可用的所有者取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**3︎⃣**：当前过滤器生成的项目可用的所有者数量。</li><li>4︎⃣：与特定所有者相关的项目数量。</li></ul></li></ul> |


### 类型

| 类型 | 描述 |
|---|---|
| ![Type](assets/projects-filters-type.png){width="300"} | **[!UICONTROL 类型]**&#x200B;部分允许您根据项目或文件夹的类型进行筛选。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 文件夹]**</li><li>**[!UICONTROL 工作区项目]**</li><li>**[!UICONTROL 移动记分卡]**</li></ul> <li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**5︎⃣**：当前过滤器生成的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定其他过滤器相关的项目数量。</li></ul></li></ul> |


### 其他过滤器

| 其他过滤器 | 描述 |
|---|---|
| ![其他过滤器](assets/projects-filters-others.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 其他过滤器]**&#x200B;部分按其他预定义过滤器进行过滤。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 显示所有]**</li><li>**[!UICONTROL 与我共享]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已批准]**</li><li>**[!UICONTROL 收藏夹]**</li></ul> 您可以选择的内容取决于您的角色和权限。</li><li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**5︎⃣**：当前过滤器生成的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定其他过滤器相关的项目数量。</li></ul></li></ul> |

## 搜索

您可以使用搜索区域 ➎ 通过![搜索](/help/assets/icons/Search.svg)字段来搜索项目和文件夹。开始输入后，[项目列表](#project-list)将会自动过滤您的搜索输入。

搜索区域还会显示从过滤器面板中应用的过滤器。

* 要移除过滤器，请选择过滤器中的 ![CrossSize75](/help/assets/icons/CrossSize75.svg)。
* 要移除所有过滤器，请选择“全部清除”。

如果空间有限，无法显示单个过滤器，您会看到&#x200B;**[!UICONTROL 按 *x* 分段的过滤器]**。

* 要移除过滤器：

   1. 使用 **[!UICONTROL *x *过滤器]**![ChevronDown](/help/assets/icons/ChevronDown.svg) 顶部打开一个上下文菜单，其中列有过滤器的类型和单个过滤器。
   1. 使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 来移除过滤器。

