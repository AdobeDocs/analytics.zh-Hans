---
title: 流媒体服务广告维度
description: 为报表包启用[!UICONTROL 媒体广告]时可用的维度。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 15%

---

# 流媒体服务广告维度

*本页介绍了为报表包启用[!UICONTROL 媒体广告]时可用的维度。 有关可用量度，请参阅[流媒体广告量度](../metrics/sm-ads.md)。*

流媒体服务和维度通过流媒体服务库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media广告]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体广告](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 广告 | 广告的唯一标识符。 | 广告开始、广告关闭 | `a.media.ad.name` |
| 广告名称（变量） | 广告的友好名称。 此外，还提供了一个名为“广告名称”的分类维度，它提供了类似用途。 此维度和分类被视为两个不同的维度。 | 广告开始、广告关闭 | `a.media.ad.friendlyName` |
| 广告播放器名称 | 呈现广告的播放器的名称。 | 广告开始、广告关闭 | `a.media.ad.playerName` |
| 广告长度（变量） | 视频广告的长度，以秒为单位。 | 广告开始、广告关闭 | `a.media.ad.length` |
| 广告pod | 广告面板的唯一标识符。 | 广告开始、广告关闭 | `a.media.ad.pod` |
| 面板中的广告位置 | 广告在父广告时间中的索引位置（0已编制索引）。 | 广告开始、广告关闭 | `a.media.ad.podPosition` |
| 广告商 | 广告中介绍的公司或品牌。 | 广告开始、广告关闭 | `a.media.ad.advertiser` |
| 营销活动 ID | 广告营销活动的 ID | 广告开始、广告关闭 | `a.media.ad.campaign` |

{style="table-layout:auto"}

除了上述维度之外，Adobe还会自动创建以下分类维度。 您必须上传分类数据，以查看使用这些维度的报表。

| 分类名称 | 父维度 | 描述 |
| --- | --- | --- |
| 资产 ID | [内容](sm-core.md) | 媒体资产内容的唯一标识符。 示例包括电视剧剧集标识符、电影资产标识符或实时事件标识符。 这些ID通常从元数据颁发机构（如EIDR、TMS/Gracenote、Rovi）或其他专有或内部系统派生。 |
| 内容评级 | [内容](sm-core.md) | 由电视节目家长指南定义的评级。 |
| 首次播放日期 | [内容](sm-core.md) | 内容首次在电视上播出的日期。由于此分类维度是一个字符串，因此允许使用任何日期格式。 Adobe建议使用一致的日期格式，如`YYYY-MM-DD`。 |
| 首次数字化日期 | [内容](sm-core.md) | 内容首次在任何数字渠道或平台上播出的日期。由于此分类维度是一个字符串，因此允许使用任何日期格式。 Adobe建议使用一致的日期格式，如`YYYY-MM-DD`。 |
| 广告长度 | 广告 | 视频广告的长度，以秒为单位。 |
| 广告名称 | 广告 | 广告的友好名称。 它是“广告名称（变量）”的等效分类。 |
| 创作 ID | 广告 | 广告创意的ID。 |
| Pod名称 | 广告pod | 广告面板的友好名称。 |
| Pod位置 | 广告pod | 广告时间在内容中的偏移，以秒为单位。 |

{style="table-layout:auto"}
