---
title: 流媒体服务章节量度
description: 为报表包启用[!UICONTROL 媒体章节]时可用的量度。
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 5%

---

# 流媒体服务章节量度

*本页介绍了为报表包启用[!UICONTROL 媒体章节]时可用的量度。 有关可用维度，请参阅[流媒体服务章节维度](../dimensions/sm-chapters.md)。*

流媒体服务章节量度通过流媒体服务收集库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体章节](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 章节完成]** | 一个布尔值，在章节完成时触发。 | 章节关闭 | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL 章节开始]** | 一个布尔值，在章节开始时触发。 | 章节开始 | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL 章节逗留时间]** | 在章节上花费的时间，以秒为单位。 | 章节关闭 | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
