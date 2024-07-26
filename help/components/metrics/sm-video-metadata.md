---
title: 流媒体视频元数据量度
description: 为报表包启用[!UICONTROL 视频元数据]时可用的量度。
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---

# 流媒体视频元数据量度

*本页介绍了为报表包启用[!UICONTROL 视频元数据]时可用的量度。 有关可用维度，请参阅[流媒体视频元数据维度](../dimensions/sm-video-metadata.md)。*

流媒体视频元数据量度通过流媒体收集库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集加载项]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 视频元数据]**&#x200B;时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 已授权 | 一个布尔值，当用户通过Adobe身份验证获得授权时触发。 | 媒体开始，媒体关闭 | `a.media.pass.auth` |

{style="table-layout:auto"}
