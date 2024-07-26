---
title: 流媒体广告量度
description: 为报表包启用[!UICONTROL 媒体广告]时可用的量度。
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---

# 流媒体广告量度

*本页介绍了为报表包启用[!UICONTROL 媒体广告]时可用的量度。 有关可用维度，请参阅[流媒体广告维度](../dimensions/sm-ads.md)。*

流媒体广告量度通过流媒体收集库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集加载项]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 媒体广告]**&#x200B;时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 广告完成 | 视频广告完成时触发。 | 广告关闭 | `a.media.ad.complete` |
| 广告开始 | 视频广告开始时触发。 | 广告开始 | `a.media.ad.view` |
| 广告逗留时间 | 观看广告所花费的总时间，以秒为单位。 | 广告关闭 | `a.media.ad.timePlayed` |
| 媒体逗留时间 | 计算所有播放事件（主内容和广告内容）的事件总时长（以秒为单位）。 | 媒体关闭 | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
