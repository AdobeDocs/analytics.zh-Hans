---
description: 在 Analysis Workspace 中使用临时区段。
title: 临时区段
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: f50e3d9a1d3c1705c55a14af0e42a0da3ac00955
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 55%

---

# 临时项目区段

利用临时项目区段，可将任何组件直接拖放到面板拖放区域中以创建区段。 该区段将变为 [项目级别区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) 当前项目的本地位置。

以下是一段关于创建临时项目区段的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. 将任意组件类型（维度、维度项、事件、指标、区段、区段模板、日期范围）拖入面板顶部的区段放置区域。组件类型会自动转换为临时区段或 [快速区段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=zh-Hans) 兼容。
以下是如何为 Twitter 反向链接域创建区段的示例：

   ![](assets/ad-hoc1.png)

   您的面板自动应用此区段，而您可立即看到结果。

1. 您可以向面板添加无限数量的区段。
1. 如果决定要保存此区段，请参阅以下部分。

请记住：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入区段区域：不能从中生成区段的指标和维度/指标。
* 对于完整的维度和事件，Analysis Workspace 将创建“存在”点击区段。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如果将“未指定”或“无”拖入区段放置区域，则它自动转换为“不存在”区段，以使其在分段时受到正确对待。

要比较可在项目中创建和应用的不同区段，请转到 [此处](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## 保存临时区段 {#ad-hoc-save}

通过保存临时区段，可以使其他项目可以使用。

1. 将光标悬停在放置区域中的区段上，然后单击“i”图标。
1. 单击编辑铅笔以转到区段生成器。
1. 检查 **[!UICONTROL 可用于所有项目并添加到组件列表]**.
1. 单击 **[!UICONTROL 保存]**.

保存后，该区段即会显示在您的左边栏组件列表中，并可以与区段管理器中的其他用户共享。
