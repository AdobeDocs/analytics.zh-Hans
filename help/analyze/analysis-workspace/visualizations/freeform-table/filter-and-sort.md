---
description: 描述如何在 Analysis Workspace 中筛选和排序表格的文档。
title: 排序和过滤表格
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 9899b5e0fbdfd5264be9d414477caad38d4550ae
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 78%

---

# 排序和过滤表格

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 只能按照本节所述过滤动态维度项目。 无法过滤静态维度项目。 有关更多信息，请参阅 [自由格式表中的动态维度项目与静态维度项目](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### 快速从表中排除特定行

您无需打开过滤器对话框即可快速从表中排除特定行。

>[!NOTE]
>
>如本节所述，排除行时， [!UICONTROL **始终排除项目**] 规则会在高级过滤器对话框中自动应用。 (您可以通过选择过滤器图标，然后 [**[!UICONTROL 显示高级]**](#apply-a-simple-or-advanced-filter-to-a-table).)

要快速从自由格式表中排除特定行，请执行以下操作：

1. 将鼠标悬停在要排除的行上，然后选择x图标。

   按住Shift键选择范围行，或按住Command键(在Mac上)或Ctrl键（在Windows上）选择多行。

### 将简单或高级过滤器应用于表

过滤自由格式表中的数据：

1. 将鼠标悬停在包含要过滤的数据的列上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 当&#x200B;**过滤器**&#x200B;图标出现时选择它。

   ![表格中的过滤器图标](assets/table-filter-icon.png)

   可以使用以下选项：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **搜索词或短语**] | 指定要按过滤的单词或短语。 仅显示包含指定单词或确切短语的行。 |
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |

1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   提供了以下高级过滤器选项：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |
   | [!UICONTROL **匹配**] | <p>选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。</p> <p>选择&#x200B;[!UICONTROL **如果满足任何条件**] 以仅显示满足您指定的任一过滤条件的数据。此选项通常会产生不太精确的数据。</p> |
   | [!UICONTROL **条件**] | <p>从以下过滤选项中选择：</p><p>（选择&#x200B;[!UICONTROL **添加行**]&#x200B;以添加多个筛选条件。您在&#x200B;[!UICONTROL **匹配**]&#x200B;部分中选择的选项决定是否必须满足您添加的所有或任何条件。）</p><ul><li><p>[!UICONTROL **包含短语**]：只有包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。<p>这是进行简单搜索时的默认设置。</p></p></li><li><p>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **对等**]：只有与您指定的短语完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </p></li></ul> |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;[!UICONTROL **应用**]&#x200B;以筛选数据。

   **过滤器**&#x200B;图标![蓝色过滤器图标过滤表格](assets/table-filter-blue-icon.png)在对表格应用过滤器时会变为蓝色。

## 对表格进行排序

您可以按 Analysis Workspace 中的任何列（量度）对自由格式表的数据进行排序。

向下箭头图标![向下箭头图标已排序表格列](assets/table-sort-arrow-icon.png)在当前排序数据的列的标题中可见。

按特定列对自由格式表中的数据进行排序：

1. 将鼠标悬停在要作为数据排序依据的列标题上。

1. 当向下箭头图标出现时选择它。

   ![向下箭头图标排序表列](assets/table-sort.png)

   表格数据按您选择的列排序。
