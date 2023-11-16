---
description: 描述如何在 Analysis Workspace 中筛选和排序表格的文档。
title: 筛选和排序自由格式表
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: e5f67042fce223f2998e4031962193b1c0154557
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 68%

---

# 筛选和排序自由格式表

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 仅可以过滤动态维度项，如本节所述。 无法筛选静态维度项目。 有关更多信息，请参阅 [自由格式表中的动态维度项与静态维度项](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## 筛选自由格式表行

您可以使用多种方法来过滤自由格式表中的行。 

- 单击行中的“X”
- 右键单击>删除选定行
- 表筛选器
- 区段

请务必阅读每种方法的影响 [自由格式表总计](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html).

### 从表中快速排除特定行

无需打开“筛选器”对话框，即可快速从表中排除特定行。

>[!NOTE]
>
>在按本节所述排除行时， [!UICONTROL **始终排除项目**] 规则将自动应用于高级过滤器对话框。 (您可以通过选择“过滤器”图标来查看应用的规则， [**[!UICONTROL 显示高级]**](#apply-a-simple-or-advanced-filter-to-a-table).)

要从自由格式表中快速排除特定行，请执行以下操作：

1. 将鼠标悬停在要排除的行上，然后选择x图标。

   按住Shift键选择一定范围的行，或按住Command键(在Mac上)或Ctrl键（在Windows上）选择多行。

### 右键单击>删除选定的行

1. 选择1行或更多行。
1. 右键单击并选择 **[!UICONTROL 删除所选行]**.

   此操作将从表中删除行并应用表过滤器。

### 对表应用简单或高级过滤器

过滤自由格式表中的数据：

1. 将鼠标悬停在包含要过滤的数据的列上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 当&#x200B;**过滤器**&#x200B;图标出现时选择它。

   ![表格中的过滤器图标](assets/table-filter-icon.png)

   可以使用以下选项：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **搜索词或短语**] | 指定要作为过滤依据的单词或短语。 仅显示包含指定单词或确切短语的行。 |
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |

1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   可以使用以下高级筛选器选项：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |
   | [!UICONTROL **匹配**] | <p>选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。</p> <p>选择&#x200B;[!UICONTROL **如果满足任何条件**] 以仅显示满足您指定的任一过滤条件的数据。此选项通常会产生不太精确的数据。</p> |
   | [!UICONTROL **条件**] | <p>从以下过滤选项中选择：</p><p>（选择&#x200B;[!UICONTROL **添加行**]&#x200B;以添加多个筛选条件。您在&#x200B;[!UICONTROL **匹配**]&#x200B;部分中选择的选项决定是否必须满足您添加的所有或任何条件。）</p><ul><li><p>[!UICONTROL **包含短语**]：只有包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。<p>这是进行简单搜索时的默认设置。</p></p></li><li><p>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **对等**]：只有与您指定的短语完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </p></li></ul> |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;[!UICONTROL **应用**]&#x200B;以筛选数据。

   **过滤器**&#x200B;图标![蓝色过滤器图标过滤表格](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)在对表格应用过滤器时会变为蓝色。

### 区段

查看我们的 [分段文档](https://docs.adobe.com/help/zh-Hans/analytics/components/segmentation/seg-home.html) 以了解更多详细信息。

## 对表格进行排序

您可以按Analysis Workspace中作为量度的任何列对自由格式表的数据进行排序。

向下箭头图标![向下箭头图标已排序表格列](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)在当前排序数据的列的标题中可见。

按特定列对自由格式表中的数据进行排序：

1. 将鼠标悬停在要作为数据排序依据的列标题上。

2. 当向下箭头图标出现时选择它。

   ![向下箭头图标排序表列](assets/table-sort.png)

   表格数据按您选择的列排序。
