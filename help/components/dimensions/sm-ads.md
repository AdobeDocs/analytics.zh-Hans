---
title: 流媒体服务广告维度
description: 为报表包启用[!UICONTROL 媒体广告]时可用的维度。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
TQID: https://experienceleague.adobe.com/5d5RQ-2dkRD-R5U0iVyApP7WdCH2O1Rsk-qlPLYJm9c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1be0f3577403db7cf9bd40ef9e7c4bfcfa6c0b17
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 2%

---

# 流媒体服务广告维度

流媒体服务和维度为通过流媒体收集库收集的数据提供补充报表功能。 这些维度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

若要使用这些维度，请为报表包启用[[!UICONTROL 媒体报告]](/help/admin/tools/manage-rs/edit-settings/media-management.md)下的&#x200B;**[!UICONTROL 媒体广告]**。

以下维度可供使用：

* [[!UICONTROL 广告]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad)
* [[!UICONTROL 面板中的广告位置]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-in-pod-position)
* [[!UICONTROL 广告长度（变量）]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length)
* [[!UICONTROL 广告名称（变量）]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name)
* [[!UICONTROL 广告播放器名称]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-player-name)
* [[!UICONTROL 广告Pod]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-pod)
* [[!UICONTROL 广告商]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/advertiser)
* [[!UICONTROL 营销活动 ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/campaign-id)

除了上述维度之外，Adobe还会自动创建以下分类维度。 您必须上传分类数据，以查看使用这些维度的报表。

| 分类名称 | 父维度 |
| --- | --- |
| [[!UICONTROL 资产ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/asset-id) | [[!UICONTROL 内容]](sm-core.md) |
| [[!UICONTROL 内容评分]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/content-rating) | [[!UICONTROL 内容]](sm-core.md) |
| [[!UICONTROL 首次播放日期]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-air-date) | [[!UICONTROL 内容]](sm-core.md) |
| [[!UICONTROL 第一个数字日期]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/first-digital-date) | [[!UICONTROL 内容]](sm-core.md) |
| [[!UICONTROL 广告长度]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-length) | [!UICONTROL 广告] |
| [[!UICONTROL 广告名称]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/ad-name) | [!UICONTROL 广告] |
| [[!UICONTROL Creative ID]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/creative-id) | [!UICONTROL 广告] |
| [[!UICONTROL 面板名称]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-name) | [!UICONTROL 广告Pod] |
| [[!UICONTROL Pod位置]](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/dimensions/pod-position) | [!UICONTROL 广告Pod] |

请参阅[流媒体服务广告量度](../metrics/sm-ads.md)以了解相应的量度。
