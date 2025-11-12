---
title: 流媒体服务视频元数据维度
description: 为报表包启用[!UICONTROL 视频元数据]时可用的维度。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---

# 流媒体服务视频元数据维度

*本页介绍了为报表包启用[!UICONTROL 视频元数据]时可用的维度。 有关可用量度，请参阅[流媒体服务视频元数据量度](../metrics/sm-video-metadata.md)。*

流媒体服务和维度通过流媒体服务收集库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[视频元数据](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 个广告加载]** | 加载的广告类型。 | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL 天部分]** | 一天中广播或播放内容的时间。 支持任何字符串值。 | 媒体开始，媒体关闭 | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL 集]** | 剧集编号。 | 媒体开始，媒体关闭 | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL 媒体馈送类型]** | 馈送的类型。 | 媒体开始，媒体关闭 | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL 流派]** | 内容制作者定义的内容类型或分组。 此维度支持多个值，并以逗号分隔。 | 媒体开始，媒体关闭 | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | MVPD由Adobe身份验证提供。 | 媒体开始，媒体关闭 | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL 网络]** | 网络或通道名称。 | 媒体开始，媒体关闭 | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL 季]** | 节目所属的季编号。 | 媒体开始，媒体关闭 | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL 节目]** | 节目或系列节目的名称。 | 媒体开始，媒体关闭 | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL 显示类型]** | 表示内容类型的整数。<br>`0`：整集<br>`1`：预览或预告片<br>`2`：剪辑<br>`3`：其他 | 媒体开始，媒体关闭 | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

