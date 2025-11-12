---
title: 流媒体服务播放器状态跟踪量度
description: 为报表包启用[!UICONTROL 播放器状态跟踪]时可用的量度。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# 流媒体服务播放器状态跟踪量度

流媒体服务播放器状态跟踪量度通过流媒体服务库为数据收集提供补充报表功能。 使用这些量度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[播放器状态跟踪](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 受隐藏式字幕影响的流数量]** | 如果在播放会话期间发生至少一次隐藏式字幕状态，则会触发。 | 媒体关闭 | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 隐藏式字幕计数]** | 视频进入“隐藏式字幕”状态的次数。 | 媒体关闭 | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 隐藏式字幕总时长]** | 视频处于“隐藏式字幕”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受全屏影响的流数量]** | 如果在播放会话期间发生至少一次全屏状态，则会触发。 | 媒体关闭 | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 全屏计数]** | 视频进入“全屏”状态的次数。 | 媒体关闭 | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 全屏总时长]** | 视频处于“全屏”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受聚焦影响的流数量]** | 如果在播放会话期间发生至少一次聚焦状态，则会触发。 | 媒体关闭 | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 聚焦计数]** | 视频进入“聚焦”状态的次数。 | 媒体关闭 | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 观看中总持续时间]** | 视频处于“聚焦”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受静音影响的流数量]** | 如果在播放会话期间发生至少一次静音状态，则会触发。 | 媒体关闭 | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 静音计数]** | 视频进入“静音”状态的次数。 | 媒体关闭 | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 静音总持续时间]** | 视频处于“静音”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受画中画影响的流数量]** | 如果在播放会话期间发生至少一次画中画状态，则会触发。 | 媒体关闭 | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL 画中画计数]** | 视频进入“画中画”状态的次数。 | 媒体关闭 | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 画中画总持续时间]** | 视频处于“画中画”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
