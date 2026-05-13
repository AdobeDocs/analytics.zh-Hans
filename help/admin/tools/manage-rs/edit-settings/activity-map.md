---
description: 启用维度，以便Activity Map能够收集数据。
title: Activity Map 报告
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 31%

---

# Activity Map 报告

允许您启用维度以用于[Activity Map](/help/analyze/activity-map/overview.md)。

**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** >选择报表包> **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map报表]**

本文档的这一部分重点介绍如何启用Activity Map使用的维度。 有关叠加、实现变量和维度的更多信息，请参阅[Activity Map概述](/help/analyze/activity-map/overview.md)。

当您选择&#x200B;**[!UICONTROL 启用Activity Map报表]**&#x200B;按钮时，将创建以下维度：

* [[!UICONTROL Activity Map 链接]](/help/components/dimensions/activity-map-link.md)：所点击的链接名称。
* [[!UICONTROL Activity Map 区域]](/help/components/dimensions/activity-map-region.md)：所点击的区域名称。
* [[!UICONTROL Activity Map 页面]](/help/components/dimensions/activity-map-page.md)：点击链接时的页面名称。
* [[!UICONTROL 按区域的 Activity Map 链接]](/help/components/dimensions/activity-map-link-by-region.md)：Activity Map 链接与 Activity Map 区域的拼接值。

启用后，您的实施可以开始将数据发送到这些维度，以在[Analysis Workspace](/help/analyze/analysis-workspace/home.md)和[浏览器扩展叠加](/help/analyze/activity-map/overlay/overview.md)中使用。

>[!NOTE]
>
>当您为报表包启用Activity Map时，它将在未来永久启用，而不会以任何方式禁用它。
