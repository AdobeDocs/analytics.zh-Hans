---
title: 流媒体服务广告量度
description: 为报表包启用[!UICONTROL 媒体广告]时可用的量度。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 流媒体服务广告量度

*本页介绍了为报表包启用[!UICONTROL 媒体广告]时可用的量度。 有关可用维度，请参阅[流媒体服务广告维度](../dimensions/sm-ads.md)。*

流媒体服务和量度通过流媒体服务库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体广告](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 广告完成]** | 视频广告完成时触发。 | 广告关闭 | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL 广告开始]** | 视频广告开始时触发。 | 广告开始 | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL 广告逗留时间]** | 观看广告所花费的总时间，以秒为单位。 | 广告关闭 | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL 媒体逗留时间]** | 计算所有“[!UICONTROL 播放]”事件（主内容和广告内容）的事件总时长（以秒为单位）。 | 媒体关闭 | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
