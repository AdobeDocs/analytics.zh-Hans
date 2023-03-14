---
description: 在Analysis Workspace中使用临时区段。
title: 临时区段
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 931e9b0bd71abd852c515cd2e7d99dc9ae423a63
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 77%

---

# 临时项目区段

通过临时项目区段，可以将任何组件直接拖放到面板拖放区域中来创建区段。 该区段将成为当前项目的本地[项目级区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F)。

以下是一段关于创建临时项目区段的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. 将任意组件类型（维度、维度项、事件、指标、区段、区段模板、日期范围）拖入面板顶部的区段放置区域。组件类型会自动转换为临时区段或 [快速区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) 如果兼容。
以下是如何为 Twitter 反向链接域创建区段的示例：

   ![](assets/ad-hoc1.png)

   您的面板自动应用此区段，而您可立即看到结果。

1. 可将无限量的区段添加到面板。
1. 如果决定要保存此区段，请参阅以下部分。

请记住：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入区段区域：不能从中生成区段的指标和维度/指标。
* 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如果将“未指定”或“无”拖入区段放置区域，则它自动转换为“不存在”区段，以使其在分段时受到正确对待。

要比较您可以在项目中创建和应用的不同区段，请转到[此处](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

## 保存临时区段 {#ad-hoc-save}

通过保存临时区段，可以将临时区段提供给其他项目。

1. 将光标悬停在放置区域中的区段上，然后单击“i”图标。
1. 单击编辑铅笔转到区段生成器。
1. 单击&#x200B;**[!UICONTROL “使其对所有项目可用，并添加到组件列表”]**。
1. 单击&#x200B;**[!UICONTROL 保存]**。

保存后，该区段将显示在左边栏组件列表中，并可从区段管理器与其他用户共享。
