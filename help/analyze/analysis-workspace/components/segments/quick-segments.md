---
description: 在 Analysis Workspace 中使用快速区段。
title: 快速区段
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 42%

---

# 快速区段

利用快速区段，您可以轻松浏览给定项目中的数据，而无需在中创建更加复杂的组件列表区段。 [区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md).

创建快速区段时，请考虑以下事项：

* 快速区段仅适用于创建它们的项目。 此类过滤器在其他项目中不可用，无法共享给其他用户。 
* 最多允许3个规则。
* 不支持嵌套容器或顺序规则。

以下视频演示了如何使用快速区段：

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 创建快速区段

Analysis Workspace中的任何用户都可以创建快速区段。

要创建快速区段，请执行以下操作：

1. 选择以下方法之一开始创建快速区段：

   * **临时（拖放）：** 从左边栏中，将组件拖到旁边的拖放区域 **区段** 图标，然后选择 **编辑** 图标来调整区段。

     ![编辑临时区段](assets/filter-adhoc-edit.png)

     >[!NOTE]
     >
     > 创建快速区段临时时（拖放），请考虑以下事项：
     > * 不支持以下组件类型：计算量度和维度，以及无法从中生成区段的量度。
     > * 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
     > * 如果将“未指定”或“无”拖入区段放置区域，则它自动转换为“不存在”区段，以使其在区段中受到正确对待。


   * **使用区段图标：** 在自由格式表中，选择 **区段** 图标来填充面板。

     ![区段过滤器](assets/quick-seg1.png)

1. 调整以下任意设置：

   | 设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 名称] | 区段的默认名称为该区段中的规则名称的组合。您可以将区段重命名为更友好的名称。 |
   | [!UICONTROL 包括/排除] | 可在区段定义中包括或排除组件，但不得既包括又排除。 |
   | [!UICONTROL “点击”/“访问”/“访客”容器] | 快速区段仅包括一个[区段容器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html#section_AF2A28BE92474DB386AE85743C71B2D6?lang=zh-Hans)，从中可在区段中包括（或从区段中排除）某个维度/量度/日期范围。[!UICONTROL 访客]包含访客在不同的访问和页面查看间专属的总体数据。 通过[!UICONTROL 访问]容器可设置规则，允许您根据访问划分访客的数据，而通过[!UICONTROL 点击]容器可根据个别页面查看划分访客信息。默认容器为[!UICONTROL 点击]。 |
   | [!UICONTROL 组件]（维度/量度/日期范围） | 通过添加组件（维度、量度、日期范围或维度值）可定义最多 3 条规则。有 3 种方法可以找到正确的组件：<ul><li>只需开始打字，快速区段生成器即自动查找相应的组件。</li><li>使用下拉列表查找组件。</li><li>从左边栏中拖放组件。</li></ul> |
   | [!UICONTROL 运算符] | 使用下拉菜单查找标准运算符和[!UICONTROL 非重复计数]运算符。请参阅 [区段运算符](/help/components/segmentation/seg-reference/seg-operators.md). |
   | 加号 (+) | 添加另一条规则。 |
   | AND/OR 限定符 | 可将“AND”或“OR”限定符添加到规则，但不得在单个区段定义中混用“AND”和“OR”。 |
   | [!UICONTROL 应用] | 将此区段应用于面板。如果该区段不包含任何数据，则系统将询问您是否要继续。 |
   | [!UICONTROL 打开生成器] | 打开区段生成器。在区段生成器中保存或应用区段后，即不再将它视为“快速区段”。 它成为组件列表区段库的一部分。 <p>要使该组件在所有项目和左边栏中都可用，请选择选项 [!UICONTROL **使此区段对所有项目都可用，并将其添加到组件列表**].</p><p>有关更多信息，请参阅部分 [将快速区段另存为组件列表区段](#save-a-quick-segment-as-a-component-list-segment) 本文章中。</p><p>**注意：** 仅限在中具有区段创建权限的用户 [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) 可以打开区段生成器。</p> |
   | [!UICONTROL 取消] | 取消此快速区段（不要应用它）。 |
   | [!UICONTROL 日期范围] | 该验证器使用面板日期范围执行其数据查找。但在快速区段中应用的任何日期范围都将取代面板顶部的面板日期范围。 |
   | 预览（右上角） | 让您查看您的区段是否有效以及该区段的作用范围。表示在应用此区段时预计将看到的数据集的划分方式。您可能会收到一条通知，表明此区段没有数据。在这种情况下，可继续操作或更改区段定义。 |

1. 选择 [!UICONTROL **应用**] 以保存更改。

## 编辑快速区段

1. 将光标悬停在快速区段上并选择 **编辑** 图标。

   ![编辑临时过滤器](assets/filter-adhoc-edit.png)

1. 编辑区段定义和/或区段名称。

1. 选择&#x200B;[!UICONTROL **应用**]。

## 将快速区段另存为组件列表区段

>[!IMPORTANT]
>
> 保存快速区段时，请考虑以下事项：
> 
> * 要保存快速区段，您需要以下项中的区段创建权限： [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).
> 
> * 保存或应用区段后，在快速区段生成器中无法再编辑该区段。 相反，您必须使用常规区段生成器。

您可以选择将快速区段另存为组件列表区段。 组件列表区段的优点包括：

* 在所有Workspace项目中均可用
* 支持更复杂的区段以及顺序区段

可从快速区段生成器中保存区段，也可从 [!UICONTROL 筛选器生成器].

### 在快速区段生成器中保存 {#save2}

1. 应用快速区段后，将光标悬停在其上并选择信息(“i”)图标。
1. 选择 **[!UICONTROL 使其对所有项目都可用，并将它添加到组件列表]**.
1. （可选）为区段重命名。
1. 选择&#x200B;**[!UICONTROL 保存]**。

   该区段现在显示在左边栏中的组件列表中。 另请注意，区段的边栏从浅蓝色变为深蓝色，这表示在快速区段生成器中无法再编辑或打开它。

### 在区段生成器中保存 {#save3}

1. 应用快速区段后，将光标悬停在其上并选择信息(“i”)图标。
1. 选择&#x200B;**[!UICONTROL “保存区段”]**
1. （可选）重命名区段，然后选择 [!UICONTROL **应用**].

   返回工作区，并注意区段的边栏从浅蓝色更改为深蓝色，这表示在快速区段生成器中无法再编辑或打开它。 通过保存它，它就成为组件列表的一部分。

应用区段后，可选择将它添加到区段组件列表，并使其对所有项目都可用。

1. 将光标悬停在保存的区段上并选择铅笔图标。

1. 选择 [!UICONTROL **打开生成器**].

1. 在区段生成器的顶部，注意 [!UICONTROL **仅用于项目的区段**] 对话框：

   ![仅用于项目的区段对话框](assets/project-only-segment-dialog.png)

1. 选中&#x200B;**[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**&#x200B;旁边的复选框。

1. 选择&#x200B;**[!UICONTROL 保存]**。

   所有项目的区段组件列表中现在都显示该区段。还可与组织中的其他人员[共享该区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans#concept_4A9726927E7C44AFA260E2BB2721AFC6)。

## 快速区段示例

以下区段示例结合了维度和量度：

![](assets/quick-seg2.png)

## 已知问题

1. 创建一个包含 2 个条目的快速区段，并将它&#x200B;**[!UICONTROL 保存]**&#x200B;为 Test1。
1. 单击&#x200B;**[!UICONTROL 另存为]**，并将此快速区段另存为 Test2。
1. 编辑 Test2 快速区段并将它再次另存为 Test2。请注意，Test1 快速区段已由 Test2 修改。
