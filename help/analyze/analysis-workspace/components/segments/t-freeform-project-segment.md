---
description: 在 Analysis Workspace 中使用区段。
title: 区段
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 0aee84be83b2e5916ecf6ffdd4171ed4ef612b5b
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 75%

---

# 区段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

您可以创建不同类型的区段，具体取决于区段的复杂程度、区段是否应仅应用于此项目等。 以下是区段类型的摘要：

| 区段类型 | 创建位置？ | 适用位置？ | 多个容器？ | UI颜色 |
| --- | --- | --- | --- |
| 组件列表区段 | [区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md) | 从左边栏到所有项目 | 是 | 蓝色 |
| 快速区段 | [快速区段生成器](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | 仅限项目级别 | 否 | 灰色? |
| 临时区段： | 请参阅下文 | 仅限项目级别 | 否 | ? |
| - Ad hoc Workspace项目区段 | 拖放到区段中？ 在新项目中 |  |  |  |
|  — 基于计算量度的区段 | 计算量度生成器 |  |  |  |
|  — 基于VRS的区段 | 虚拟报表包生成器 |  |  |  |
|  — 区段生成器“应用” | 区段生成器 |  |  |  |

有关Adobe Analytics中分段的深入讨论，请前往[此处](/help/components/segmentation/seg-overview.md)。

## 左边栏中的组件列表区段 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

“组件”菜单下方的区段边栏会同时显示区段和区段模板，由以下图标指示：

![](assets/segment_icons.png)

[在 Analysis Workspace 中使用区段](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-in-analysis-workspace.html?lang=zh-Hans)（6 分 46 秒）

## Analysis Workspace中的临时（临时）区段

以下是有关临时区段的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

## 创建区段 {#section_693CFADA668B4542B982446C2B4CF0F5}

将任意组件类型（维度、维度项目、事件、量度、区段、区段模板和日期范围）放入面板顶部的区段拖放区域中，即可创建即时区段。

组件类型将被自动转换为区段。或者，您还可以单击“添加区段”下拉框中的“+”号。

请记住以下事项：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入区段区域：不能从中生成区段的量度和维度/量度。
* 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：“点击存在 eVar1 的地方”或“点击存在 event1 的地方”。
* 如果将“未指定”或“无”放入区段下拉区域中，它们将自动转换为“不存在”区段，以便在分段时正确进行处理。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>通过这种方式创建的区段是项目的内部区段。

您可以选择按照以下步骤操作，将这些区段设为公用（全局）区段：

1. 在拖放区域中将光标悬停区段上，然后单击“i”图标。
1. 在显示的信息面板中，单击&#x200B;**[!UICONTROL 设为公用]**。

   ![](assets/segment-info.png)

## 应用区段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

还有其他一些方法也可以将区段应用到自由格式项目中。

| 操作 | 描述 |
|--- |--- |
| 从选定范围中创建区段 | 创建内联区段。选择行，接着右键单击选定的内容，然后创建内联区段。该区段只适用于打开的项目并且不能另存为 Analytics 区段。1. 选择行。2. 右键单击选定的内容。3. 单击&#x200B;*从选定范围中创建区段*。 |
| 组件 > 新建区段 | 屏幕上会显示“区段生成器”。有关区段划分的更多信息，请参阅[区段生成器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hans)。 |
| “共享”>“共享项目”或“共享”>“策划项目数据” | 在[组织并共享](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，了解应用到项目中的区段如何用于为收件人提供的共享分析报表。 |
| 使用区段作为维度 | 视频：[在 Analysis Workspace 中使用区段作为维度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=en) |


