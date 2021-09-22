---
description: 在Analysis Workspace中使用快速区段。
title: 快速区段
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# 快速区段

您可以在项目中创建快速区段，以绕过完整[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)的复杂性。 要比较快速区段可以执行的操作与完整的组件列表区段，请前往[此处](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

>[!IMPORTANT]
> 快速区段当前处于有限测试中，通常还不可用。

## 创建快速区段

1. 在自由格式表中，单击面板标题中的过滤器+图标：

   ![](assets/quick-seg1.png)

   请注意:

   - 只有一个区段容器允许您在区段中包含维度/量度/日期范围（或将其从区段中排除）。
   - 您可以将容器设置为“点击”、“访问”或“访客”级别。 默认为“点击”。

1. 通过以下三种方式之一添加维度/量度/日期范围：

   - 开始键入内容，[!UICONTROL 快速区段生成器]会自动找到相应的组件。
   - 使用下拉列表查找组件。
   - 从左边栏拖放组件。

1. 指定第一个规则，如`Page equals workspace`。 一个区段定义中最多可以有三个规则。 只需单击“+”符号即可添加其他规则。 您可以在规则中添加“AND”或“OR”限定符，但不能在单个区段定义中混合使用“AND”和“OR”。

   以下是将维度和量度组合在一起的区段示例：

   ![](assets/quick-seg2.png)

1. 单击&#x200B;**[!UICONTROL Apply]**以将此区段应用到面板。
区段显示在顶部。 请注意其灰色侧栏，而不是左侧区段库中组件级别区段的蓝色侧栏。

   ![](assets/quick-seg3.png)

## 编辑快速区段

1. 将鼠标悬停在快速区段上，然后选择铅笔图标。
1. 编辑区段定义或区段名称。

## 保存快速区段

您可以选择按照以下步骤来保存快速区段。

>[!IMPORTANT]
>保存或应用区段后，您便无法再在快速区段生成器中编辑该区段，只能在常规的区段生成器中进行编辑。

1. 将鼠标悬停在快速区段上，然后选择信息(“i”)图标。
1. 选择&#x200B;**[!UICONTROL 保存区段]**

   ![](assets/save-quick-seg.png)

1. 保留名称为原样，或重命名区段。

   返回到工作区，并注意区段现在如何显示蓝色侧栏。 这表示无法在快速区段生成器中编辑/打开该区段。 通过保存，它将成为组件列表的一部分。

   ![](assets/quick-seg4.png)

应用区段后，您可以选择将其添加到区段组件列表，并使其可用于所有项目。

1. 将鼠标悬停在保存的区段上，然后选择铅笔图标。

1. 在区段生成器顶部，请注意以下对话框：

   ![](assets/project-only.png)

1. 选中&#x200B;**[!UICONTROL 使此区段对所有项目都可用旁边的复选框，并将其添加到组件列表。]**
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 现在，该区段会显示在您所有项目的区段组件列表中。
1. 您还可以[与组织中的其他人员共享区段](/help/components/segmentation/segmentation-workflow/t-seg-share.md)。

## 什么是仅限项目的区段？

仅项目区段是快速区段或临时工作区项目区段。 在区段生成器中编辑/打开区段时，将显示“仅限项目”框。 如果在生成器中应用快速区段，但未选中“可用”框，则它仍是仅限项目的区段，但无法再在QS生成器中打开。 如果选中框并执行保存，则该区段现在为组件列表区段。