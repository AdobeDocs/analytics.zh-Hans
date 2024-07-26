---
title: 流媒体音频元数据维度
description: 为报表包启用[!UICONTROL 音频元数据]时可用的维度。
feature: Dimensions
source-git-commit: 45b371bd20223b86d0f17d9bdb48cffb2de15468
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 8%

---

# 流媒体音频元数据维度

流媒体广告维度通过流媒体收集库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集加载项]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 音频元数据]**&#x200B;时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 专辑 | 专辑的名称。 | 媒体开始，媒体关闭 | `a.media.album` |
| 艺人 | 艺人的姓名。 | 媒体开始，媒体关闭 | `a.media.artist` |
| 作者 | 有声读物作者的姓名。 | 媒体开始，媒体关闭 | `a.media.author` |
| 标签 | 记录标签的名称。 | 媒体开始，媒体关闭 | `a.media.label` |
| 发布者 | 音频内容发布者的名称。 | 媒体开始，媒体关闭 | `a.media.publisher` |
| 电台/电视台 | 无线电台的名称或ID。 | 媒体开始，媒体关闭 | `a.media.station` |

{style="table-layout:auto"}
