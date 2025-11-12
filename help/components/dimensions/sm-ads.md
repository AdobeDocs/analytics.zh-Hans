---
title: 流媒体服务广告维度
description: 为报表包启用[!UICONTROL 媒体广告]时可用的维度。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# 流媒体服务广告维度

*本页介绍了为报表包启用[!UICONTROL 媒体广告]时可用的维度。 有关可用量度，请参阅[流媒体广告量度](../metrics/sm-ads.md)。*

流媒体服务和维度通过流媒体服务库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体广告](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 广告]** | 广告的唯一标识符。 | 广告开始、广告关闭 | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL 广告名称（变量）]** | 广告的友好名称。 名为“[!UICONTROL 广告名称]”的分类维度也可用，它提供了类似的用途。 此维度和分类被视为两个不同的维度。 | 广告开始、广告关闭 | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL 广告播放器名称]** | 呈现广告的播放器的名称。 | 广告开始、广告关闭 | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL 广告长度（变量）]** | 视频广告的长度，以秒为单位。 | 广告开始、广告关闭 | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL 广告Pod]** | 广告面板的唯一标识符。 | 广告开始、广告关闭 | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL 面板中的广告位置]** | 广告在父广告时间中的索引位置（0已编制索引）。 | 广告开始、广告关闭 | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL 广告商]** | 广告中介绍的公司或品牌。 | 广告开始、广告关闭 | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL 营销活动 ID]** | 广告营销活动的 ID | 广告开始、广告关闭 | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

除了上述维度之外，Adobe还会自动创建以下分类维度。 您必须上传分类数据，以查看使用这些维度的报表。

| 分类名称 | 父维度 | 描述 |
| --- | --- | --- |
| **[!UICONTROL 资产ID]** | [[!UICONTROL 内容]](sm-core.md) | 媒体资产内容的唯一标识符。 示例包括电视剧剧集标识符、电影资产标识符或实时事件标识符。 这些ID通常从元数据颁发机构（如EIDR、TMS/Gracenote、Rovi）或其他专有或内部系统派生。 |
| **[!UICONTROL 内容评级]** | [[!UICONTROL 内容]](sm-core.md) | 由电视节目家长指南定义的评级。 |
| **[!UICONTROL 首次播放日期]** | [[!UICONTROL 内容]](sm-core.md) | 内容首次在电视上播出的日期。 由于此分类维度是一个字符串，因此允许使用任何日期格式。 Adobe建议使用一致的日期格式，如`YYYY-MM-DD`。 |
| **[!UICONTROL 第一个数字日期]** | [[!UICONTROL 内容]](sm-core.md) | 内容首次在任何数字渠道或平台上播出的日期。 由于此分类维度是一个字符串，因此允许使用任何日期格式。 Adobe建议使用一致的日期格式，如`YYYY-MM-DD`。 |
| **[!UICONTROL 广告长度]** | [!UICONTROL 广告] | 视频广告的长度，以秒为单位。 |
| **[!UICONTROL 广告名称]** | [!UICONTROL 广告] | 广告的友好名称。 它是“[!UICONTROL 广告名称（变量）]”的等效分类。 |
| **[!UICONTROL Creative ID]** | [!UICONTROL 广告] | 广告创意的ID。 |
| **[!UICONTROL 面板名称]** | [!UICONTROL 广告Pod] | 广告面板的友好名称。 |
| **[!UICONTROL Pod位置]** | [!UICONTROL 广告Pod] | 广告时间在内容中的偏移，以秒为单位。 |
