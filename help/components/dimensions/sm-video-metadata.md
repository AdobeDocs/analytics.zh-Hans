---
title: 流媒体视频元数据维度
description: 为报表包启用[!UICONTROL 视频元数据]时可用的维度。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# 流媒体视频元数据维度

*本页介绍了为报表包启用[!UICONTROL 视频元数据]时可用的维度。 有关可用量度，请参阅[流媒体视频元数据量度](../metrics/sm-video-metadata.md)。*

流媒体广告维度通过流媒体收集库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 视频元数据]**&#x200B;时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 广告加载次数 | 加载的广告类型。 | 待定 | `a.media.adLoad` |
| 播出时段 | 一天中广播或播放内容的时间。 支持任何字符串值。 | 媒体开始，媒体关闭 | `a.media.dayPart` |
| 剧集 | 剧集编号。 | 媒体开始，媒体关闭 | `a.media.episode` |
| 媒体馈送类型 | 馈送的类型。 | 媒体开始，媒体关闭 | `a.media.feed` |
| 流派 | 内容制作者定义的内容类型或分组。 此维度支持多个值，并以逗号分隔。 | 媒体开始，媒体关闭 | `a.media.genre` |
| MVPD | 由Adobe身份验证提供的MVPD。 | 媒体开始，媒体关闭 | `a.media.pass.mvpd` |
| 网络 | 网络或渠道名称 | 媒体开始，媒体关闭 | `a.media.network` |
| 季 | 节目所属的季编号。 | 媒体开始，媒体关闭 | `a.media.season` |
| 节目 | 节目或系列节目的名称。 | 媒体开始，媒体关闭 | `a.media.show` |
| 显示类型 | 表示内容类型的整数。<br>`0`：整集<br>`1`：预览或预告片<br>`2`：剪辑<br>`3`：其他 | 媒体开始，媒体关闭 | `a.media.type` |

{style="table-layout:auto"}
