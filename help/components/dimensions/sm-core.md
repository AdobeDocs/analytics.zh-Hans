---
title: 流媒体服务核心维度
description: 为报表包启用[!UICONTROL 媒体核心]时可用的维度。
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 9%

---

# 流媒体服务核心维度

*本页介绍了为报表包启用[!UICONTROL 媒体核心]时可用的维度。 有关可用量度，请参阅[流媒体服务核心量度](../metrics/sm-core.md)。*

流媒体服务核心维度为通过流媒体服务库收集的数据提供基本报表功能。 使用这些维度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media广告]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体核心](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 内容 | 内容的内容ID。 | 媒体开始，媒体关闭 | `a.media.name` |
| 内容渠道 | 播放内容的分发站点或渠道。 任何字符串值都有效。 | 媒体开始，媒体关闭 | `a.media.channel` |
| 内容时长（变量） | 所用内容的最大长度（或持续时间），以秒为单位。 多个量度需要此维度，包括“平均受众访问分钟数”。 如果未设置此维度，则从属量度将不可用。<br><br>名为“视频长度”的分类维度也可用，它提供了类似目的。 此维度和分类被视为两个不同的维度。 | 媒体开始，媒体关闭 | `a.media.length` |
| 内容名称（变量） | 内容的友好名称。 此外，还提供了名为“视频名称”的分类，它提供了类似用途。 此维度和分类被视为两个不同的维度。 | 媒体开始，媒体关闭 | `a.media.friendlyName` |
| 内容播放器名称 | 内容播放器的名称。 | 媒体开始，媒体关闭 | `a.media.playerName` |
| 内容区段 | 描述已查看的内容部分的间隔，以分钟为单位。 区段在播放会话期间计算为播放头的最小值和最大值。 | 媒体关闭 | `a.media.segment` |
| 内容类型 | 内容的类型。 有效值包括`song`、`podcast`、`audiobook`、`radio`、`VoD`、`Live`、`Linear`、`UGC`、`DVoD`或自定义值。 | 媒体开始，媒体关闭 | `a.contentType` |
| 媒体路径 | 访客访问内容所使用的路径。 | 媒体开始 | `a.media.path` |
| 流类型 | 流类型。有效值包括 `audio` 和 `video`。 | 媒体开始，媒体关闭 | `a.media.streamType` |

{style="table-layout:auto"}

除了上述维度之外，Adobe还会自动创建以下分类维度。 您必须上传分类数据，以查看使用这些维度的报表。

| 分类名称 | 父维度 | 描述 |
| --- | --- | --- |
| 视频长度 | 内容 | 所用内容的最大长度（或持续时间），以秒为单位。 依赖于内容长度的量度不能使用此分类；您必须创建一个计算量度以使用此分类获取“平均受众访问分钟数”等量度。 |
| 视频名称 | 内容 | 内容的友好名称。 它是内容名称（变量）的等效分类。 |

{style="table-layout:auto"}
