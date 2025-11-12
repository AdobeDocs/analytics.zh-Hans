---
title: 流媒体服务核心量度
description: 为报表包启用[!UICONTROL 媒体核心]时可用的量度。
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# 流媒体服务核心量度

*本页介绍了为报表包启用[!UICONTROL 媒体核心]时可用的量度。 有关可用维度，请参阅[流媒体服务核心维度](../dimensions/sm-core.md)。*

流媒体服务核心量度为通过流媒体服务收集库收集的数据提供基本报表功能。 使用这些量度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体核心](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均受众访问分钟数]** | 在给定内容上花费的总时间除以该内容所有播放会话的时长。<br>`[Time spent] / [Media length]` | 媒体关闭 | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL 内容完成]** | 当一段内容完成时触发。 此量度并不一定意味着他们查看了整个内容；他们可以跳过前面。 这仅意味着它们到达了内容的结尾。 | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL 受暂停影响的流]** | 如果在内容播放期间发生了一次或多次暂停，则会触发的布尔值。 | 媒体关闭 | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL 暂停事件]** | 播放会话期间发生的暂停计数。 | 媒体关闭 | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL 总暂停持续时间]** | 所有暂停事件的总持续时间（以秒为单位）。 | 媒体关闭 | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL 内容开始]** | 第一帧媒体被占用。 如果用户在广告期间或缓冲期间放弃观看，则不会触发此事件。 | 媒体关闭 | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10%进度标记]**<br>**[!UICONTROL 25%进度标记]**<br>**[!UICONTROL 50%进度标记]**<br>**[!UICONTROL 75%进度标记]**<br>**[!UICONTROL 95%进度标记]** | 根据长度，播放头经过指示的内容标记。 每个标记仅计数一次，即使向后搜索也是如此。 如果向前搜索，则跳过的标记不会被计数。 | 媒体关闭 | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL 内容继续]** | 一个布尔值，当内容在缓冲、暂停或停滞时间超过30分钟后恢复时触发。 如果播放器在VideoInfo trackPlay中进行设置，也会触发。 | 媒体关闭 | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL 内容区段视图]** | 一个布尔值，在查看的区段的第一帧触发。 | 媒体关闭 | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL 媒体开始]** | 一个布尔值，媒体最初加载时触发。 此事件包括广告、缓冲和错误。 | 媒体开始 | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL 内容逗留时间]** | 主内容中所有“播放”类型事件的事件总持续时间（以秒为单位）。 | 媒体关闭 | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL 唯一播放时间]** | 独特内容播放的总时间，以秒为单位。 此量度不包括查看重复内容（例如向后搜索）时播放的时间。 | 媒体关闭 | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
