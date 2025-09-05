---
description: 启用维度，以便Activity Map能够收集数据。
title: Activity Map 报表功能
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Activity Map 报表功能

允许您启用维度以用于[Activity Map](/help/analyze/activity-map/overview.md)。

**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** >选择报表包> **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map报表]**

本文档的这一部分重点介绍如何启用Activity Map使用的维度。 有关叠加、实现变量和维度的更多信息，请参阅[Activity Map概述](/help/analyze/activity-map/overview.md)。

当您选择&#x200B;**[!UICONTROL 启用Activity Map报表]**&#x200B;按钮时，将创建以下维度：

* [[!UICONTROL Activity Map链接]](/help/components/dimensions/activity-map-link.md)：已单击的链接名称。
* [[!UICONTROL Activity Map地区]](/help/components/dimensions/activity-map-region.md)：被点击的地区名称。
* [[!UICONTROL Activity Map页面]](/help/components/dimensions/activity-map-page.md)：链接被单击时的页面名称。
* [[!UICONTROL 按地区]](/help/components/dimensions/activity-map-link-by-region.md)列出的Activity Map链接： Activity Map链接与Activity Map地区的拼接值。

启用后，您的实施可以开始将数据发送到这些维度，以在[Analysis Workspace](/help/analyze/analysis-workspace/home.md)和[浏览器扩展叠加](/help/analyze/activity-map/overlay/overview.md)中使用。

>[!NOTE]
>
>当您为报表包启用Activity Map时，它将在未来永久启用，而不会以任何方式禁用它。
