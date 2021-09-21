---
description: 在Analysis Workspace中使用快速区段。
title: 快速区段
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# 快速区段

您可以在项目中创建快速区段，以绕过完整[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)的复杂性。 要比较快速区段可以执行的操作与完整的组件级别区段，请访问[此处](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

>[!IMPORTANT]
> 快速区段当前处于有限测试中，通常还不可用。

## 创建快速区段

1. 在自由格式表中，单击面板标题中的过滤器+图标：

   ![](assets/quick-seg1.png)

   请注意:

   - 只有一个区段容器允许您在区段中包含维度/量度/日期范围（或将其从区段中排除）。
   - 您可以将容器设置为“点击”、“访问”或“访客”级别。 默认为“点击”。

1. 通过以下三种方式之一添加维度/量度/日期范围：

   - 开始键入内容，快速区段生成器会自动找到相应的组件。
   - 使用下拉列表查找组件。
   - 从左边栏拖放组件。

1. 指定第一个规则，如`Page equals workspace`。 区段定义中最多可包含三个规则。 只需单击“+”符号即可添加其他规则。 您可以在规则中添加“AND”或“OR”限定符，但不能在单个区段定义中混合使用“AND”和“OR”。

   以下是将维度和量度组合在一起的区段示例：

   ![](assets/quick-seg2.png)

1. 单击&#x200B;**[!UICONTROL Apply]**以将此区段应用到面板。
区段显示在顶部。 请注意其灰色侧栏，而不是左侧组件级别区段的蓝色条。

   ![](assets/quick-seg3.png)

## 将快速区段设为公用

您可以选择按照以下步骤操作，将这些区段设为公用（全局）区段：

1. 将鼠标悬停在快速区段上，然后单击“i”图标。
1. 单击&#x200B;**[!UICONTROL 打开生成器]**。
这会在区段生成器中打开该区段。
   >[!NOTE]
   >在区段生成器中应用或保存区段后，便无法再在快速区段生成器中对其进行编辑。
1. 单击&#x200B;**[!UICONTROL 确定]**。
1. 在区段生成器中，单击&#x200B;**[!UICONTROL 应用]**。
1. 返回到工作区，并注意区段现在如何显示蓝色侧栏，指示它是组件库的一部分。

   ![](assets/quick-seg4.png)

