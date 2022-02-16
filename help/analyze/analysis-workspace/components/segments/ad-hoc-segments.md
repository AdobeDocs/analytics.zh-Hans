---
description: 在 Analysis Workspace 中使用临时区段。
title: 临时区段
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 100%

---

# 临时项目区段

以下是一段关于创建临时项目区段的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

如果要快速探索区段可能如何影响您的项目，但不转到区段生成器，则可创建临时项目区段。请将这些区段视为暂时、项目级别的区段。它们一般不像左边栏中的组件区段那样将成为您区段“库”的一部分。但是，也可保存它们，如下所示。

要比较临时项目区段与完整的组件级区段的作用，请转到[此处](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

1. 将任意组件类型（维度、维度项、事件、指标、区段、区段模板、日期范围）拖入面板顶部的区段放置区域。随后组件类型自动转换为区段。以下是如何为 Twitter 反向链接域创建区段的示例：

   ![](assets/ad-hoc1.png)

   您的面板自动应用此区段，而您可立即看到结果。

1. 可将无限量的组件添加到面板。
1. 如果决定要保存此区段，请参阅以下部分。

请记住：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入区段区域：不能从中生成区段的指标和维度/指标。
* 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如果将“未指定”或“无”拖入区段放置区域，则它自动转换为“不存在”区段，以使其在分段时受到正确对待。

>[!NOTE]
>
>通过这种方式创建的区段是项目的内部区段。

## 保存临时项目区段 {#ad-hoc-save}

可选择按以下这些步骤保存这些区段：

1. 将光标悬停在放置区域中的区段上，然后单击“i”图标。
1. 在随后显示的信息面板中单击&#x200B;**[!UICONTROL “保存”]**。

   ![](assets/segment-info.png)

## 仅用于项目的区段是什么？

仅用于项目的区段或者是快速区段，或者是临时工作区项目区段。在区段生成器中编辑/打开此类区段时，将出现表示仅用于项目的框。如果在生成器中应用某个快速区段，但未选中使其可用的框，则它仍为仅用于项目的区段，但在快速区段生成器中无法再打开它。如果选中该框并“保存”，则它现在为组件列表区段。
