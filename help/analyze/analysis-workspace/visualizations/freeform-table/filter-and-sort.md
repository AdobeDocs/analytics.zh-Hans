---
description: 描述如何在 Analysis Workspace 中筛选和排序表格的文档。
title: 排序和过滤表格
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 76%

---

# 排序和过滤表格

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 如本節所述，只能篩選動態維度專案。 無法篩選靜態維度專案。 如需詳細資訊，請參閱 [自由表格中的動態與靜態維度專案](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### 從表格中快速排除特定列

您可以快速從表格中排除特定列，而無需開啟「篩選」對話方塊。

>[!NOTE]
>
>如本節所述，排除列時， [!UICONTROL **一律排除專案**] 規則會自動套用至進階篩選對話方塊。 (您可以選取「篩選」圖示，然後選取「 」，檢視套用的規則 [**[!UICONTROL 顯示進階]**](#apply-a-simple-or-advanced-filter-to-a-table).)

若要從自由表格中快速排除特定列：

1. 暫留在您要排除的列上，然後選取x圖示。

   按住Shift鍵以選取範圍列，或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）以選取多個列。

### 套用簡單或進階篩選器至表格

过滤自由格式表中的数据：

1. 將游標停留在包含您要篩選之資料的欄上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 当&#x200B;**过滤器**&#x200B;图标出现时选择它。

   ![表格中的过滤器图标](assets/table-filter-icon.png)

   可以使用以下选项：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **搜尋字詞或片語**] | 指定您要篩選的字詞或片語。 仅显示包含指定单词或确切短语的行。 |
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |

1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   可使用下列進階篩選選項：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **包括未指定的项（无）**] | 选择此选项可在表中显示不属于表格的任何维度的数据。<!--what is this?--> |
   | [!UICONTROL **匹配**] | <p>选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。</p> <p>选择&#x200B;[!UICONTROL **如果满足任何条件**] 以仅显示满足您指定的任一过滤条件的数据。此选项通常会产生不太精确的数据。</p> |
   | [!UICONTROL **条件**] | <p>从以下过滤选项中选择：</p><p>（选择&#x200B;[!UICONTROL **添加行**]&#x200B;以添加多个筛选条件。您在&#x200B;[!UICONTROL **匹配**]&#x200B;部分中选择的选项决定是否必须满足您添加的所有或任何条件。）</p><ul><li><p>[!UICONTROL **包含短语**]：只有包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。<p>这是进行简单搜索时的默认设置。</p></p></li><li><p>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</p></li><li><p>[!UICONTROL **对等**]：只有与您指定的短语完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </p></li><li><p>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </p></li></ul> |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;[!UICONTROL **应用**]&#x200B;以筛选数据。

   **过滤器**&#x200B;图标![蓝色过滤器图标过滤表格](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)在对表格应用过滤器时会变为蓝色。

## 对表格进行排序

您可以按 Analysis Workspace 中的任何列（量度）对自由格式表的数据进行排序。

向下箭头图标![向下箭头图标已排序表格列](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)在当前排序数据的列的标题中可见。

按特定列对自由格式表中的数据进行排序：

1. 将鼠标悬停在要作为数据排序依据的列标题上。

2. 当向下箭头图标出现时选择它。

   ![向下箭头图标排序表列](assets/table-sort.png)

   表格数据按您选择的列排序。
