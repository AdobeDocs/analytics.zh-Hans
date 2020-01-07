---
description: 'null'
title: 区段
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 区段 {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## 区段边栏 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

“组件”菜单下方的区段边栏会同时显示区段和区段模板，由以下图标指示：

![](assets/segment_icons.png)

[YouTube 上的使用 Analysis Workspace 中的区段](https://www.youtube.com/watch?v=QlUCdQDnni4) (6:46)

## 创建区段 {#section_693CFADA668B4542B982446C2B4CF0F5}

将任意组件类型（维度、维度项目、事件、量度、区段、区段模板和日期范围）放入面板顶部的区段拖放区域中，即可创建即时区段。

组件类型将被自动转换为区段。或者，您还可以单击“添加区段”下拉框中的“+”号。

请记住以下事项：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入区段区域：不能从中生成区段的量度和维度/量度。
* 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：“在 eVar1 存在的地方点击”或“在 event1 存在的地方点击”。
* 如果将“未指定”或“无”放入区段下拉区域中，它们将自动转换为“不存在”区段，以便在分段时正确进行处理。

![](assets/segment-dropzone.png)

> [!NOTE] 通过这种方式创建的区段是项目的内部区段。

您可以选择按照以下步骤操作，将这些区段设为公用（全局）区段：

1. 在拖放区域中将光标悬停区段上，然后单击“i”图标。
1. 在显示的信息面板中，单击&#x200B;**[!UICONTROL 设为公用]**。

   ![](assets/segment-info.png)

## 应用区段的其他方法 {#section_10FF2E309BA84618990EA5B473015894}

还有其他一些方法也可以将区段应用到自由格式项目中。

| 操作 | 描述 |
|--- |--- |
| 从选定范围中创建区段 | 创建内联区段。选择行，接着右键单击选定的内容，然后创建内联区段。该区段只适用于打开的项目并且不能另存为 Analytics 区段。1. 选择行。2. 右键单击选定的内容。3. 单击&#x200B;*从选定范围中创建区段*。 |
| 组件 &gt; 新建区段 | 屏幕上会显示“区段生成器”。有关区段划分的更多信息，请参阅[区段生成器](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html)。 |
| “共享”&gt;“共享项目”或“共享”&gt;“策划项目数据” | 在[组织并共享](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，了解应用到项目中的区段如何用于为收件人提供的共享分析报表。 |
| 使用区段作为维度 | 视频：[在 Analysis Workspace 中使用区段作为维度](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
