---
title: 流媒体质量维度
description: 为报表包启用[!UICONTROL 媒体质量]时可用的维度。
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# 流媒体质量维度

*本页介绍了为报表包启用[!UICONTROL 媒体质量]时可用的维度。 有关可用量度，请参阅[流媒体质量量度](../metrics/sm-quality.md)。*

流媒体质量维度提供与访客使用的内容质量相关的报表。 使用这些维度需要[!UICONTROL Adobe流媒体收藏集]。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 媒体质量]**&#x200B;时，以下维度可用：

| Dimension名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 平均比特率 | 以100-KBPS存储段间隔表示的平均比特率。 其计算为与给定播放会话的播放持续时间相关的所有比特率值的加权平均值。 | 媒体关闭 | `a.media.qoe.bitrateAverageBucket` |
| 比特率更改 | 播放会话期间发生比特率更改的次数。 | 媒体关闭 | `a.media.qoe.bitrateChangeCount` |
| 缓冲事件 | 媒体播放器在播放会话期间进入缓冲状态的次数。 | 媒体关闭 | `a.media.qoe.bufferCount` |
| 缓冲总持续时间 | 缓冲所花费的总时间，以秒为单位。 | 媒体关闭 | `a.media.qoe.bufferTime` |
| 丢帧 | 播放会话期间发生的丢帧总数。 | 媒体关闭 | `a.media.qoe.droppedFrameCount` |
| 错误数 | 播放会话期间发生的错误总数。 | 媒体关闭 | `a.media.qoe.errorCount` |
| 外部错误Id | 来自任何外部源的所有唯一错误ID，如CDN错误。 您必须提供所需的错误代码或ID。 允许多个错误ID。 | 媒体关闭 | `a.media.qoe.externalErrors` |
| 播放器SDK错误ID | 内容播放器SDK生成的所有唯一错误ID。 您必须提供所需的错误代码或ID。 允许多个错误ID。 | 媒体关闭 | `a.media.qoe.playerSdkErrors` |
| 开始时间 | 如果未通过QoSObject设置，则此值默认为`0`。 设置值（以毫秒为单位）。 Analysis Workspace以秒为单位报告此维度。 | 媒体开始，媒体关闭 | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
