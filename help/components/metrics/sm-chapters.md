---
title: 流媒体章节量度
description: 为报表包启用[!UICONTROL 媒体章节]时可用的量度。
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# 流媒体章节量度

*本页介绍了为报表包启用[!UICONTROL 媒体章节]时可用的量度。 有关可用维度，请参阅[流媒体章节维度](../dimensions/sm-chapters.md)。*

流媒体章节量度通过流媒体收集库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集加载项]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 媒体章节]**&#x200B;时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 章节结束 | 一个布尔值，在章节完成时触发。 | 章节关闭 | `a.media.chapter.complete` |
| 章节开始 | 一个布尔值，在章节开始时触发。 | 章节开始 | `a.media.chapter.view` |
| 章节逗留时间 | 在章节上花费的时间，以秒为单位。 | 章节关闭 | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
