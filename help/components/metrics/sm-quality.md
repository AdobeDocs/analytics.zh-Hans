---
title: 流媒体质量量度
description: 为报表包启用[!UICONTROL 媒体质量]时可用的量度。
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# 流媒体质量量度

*本页介绍了为报表包启用[!UICONTROL 媒体质量]时可用的量度。 有关可用维度，请参阅[流媒体质量维度](../dimensions/sm-quality.md)。*

流媒体质量量度通过流媒体收集库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集加载项]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 媒体质量]**&#x200B;时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 平均比特率 | 播放会话的播放持续时间的所有比特率值的加权平均值。 | 媒体关闭 | `a.media.qoe.bitrateAverage` |
| 受比特率更改影响的流 | 一个布尔值，在播放会话期间如果比特率至少更改一次，则会触发该布尔值。 | 媒体关闭 | `a.media.qoe.bitrateChange` |
| 比特率更改 | 比特率更改的次数。 | 媒体关闭 | `a.media.qoe.bitrateChangeCount` |
| 受缓冲影响的流 | 一个布尔值，在视频至少一次进入缓冲状态时触发。 | 媒体关闭 | `a.media.qoe.buffer` |
| 缓冲事件 | 视频在播放会话期间进行缓冲的次数。 | 媒体关闭 | `a.media.qoe.bufferCount` |
| 缓冲总持续时间 | 视频在所有缓冲事件中缓冲所花费的时间，以秒为单位。 | 媒体关闭 | `a.media.qoe.bufferTime` |
| 开始前丢帧 | 一个布尔值，当用户在视频的主要内容开始之前退出时触发。 | 媒体关闭 | `a.media.qoe.dropBeforeStart` |
| 丢帧 | 一个整数，表示在播放会话期间丢帧的总数。 | 媒体关闭 | `a.media.qoe.droppedFrameCount` |
| 受丢帧影响的流 | 一个布尔值，当播放会话期间任何帧丢失时触发。 | 媒体关闭 | `a.media.qoe.droppedFrames` |
| 受错误影响的流 | 一个布尔值，当视频在播放会话期间任何时候遇到错误时触发。 | 媒体关闭 | `a.media.qoe.error` |
| 错误事件 | 一个整数，表示在播放会话期间遇到的错误总数。 | 媒体关闭 | `a.media.qoe.errorCount` |
| 开始时间 | 启动视频所用的时间（以毫秒为单位）。 Adobe以秒为单位转换和存储此值。 | 媒体关闭 | `a.media.qoe.timeToStart` |
