---
title: 流媒体播放器状态跟踪量度
description: 为报表包启用[!UICONTROL 播放器状态跟踪]时可用的量度。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# 流媒体播放器状态跟踪量度

流媒体播放器状态跟踪量度通过流媒体收集库为数据收集提供补充报告功能。 使用这些量度需要&#x200B;**[!UICONTROL Adobe流媒体收藏集]**。 有关详细信息，请与您的Adobe客户团队联系。

当您在[媒体报告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下启用&#x200B;**[!UICONTROL 播放器状态跟踪]**&#x200B;时，以下量度可用：

| 量度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 受隐藏式字幕影响的流数量 | 如果在播放会话期间发生至少一次隐藏式字幕状态，则会触发。 | 媒体关闭 | `a.media.states.closedcaptioning.set` |
| 隐藏式字幕计数 | 视频进入“隐藏式字幕”状态的次数。 | 媒体关闭 | `a.media.states.closedcaptioning.count` |
| 隐藏式字幕总时长 | 视频处于“隐藏式字幕”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.closedcaptioning.time` |
| 受全屏影响的流数量 | 如果在播放会话期间发生至少一次全屏状态，则会触发。 | 媒体关闭 | `a.media.states.fullscreen.set` |
| 全屏计数 | 视频进入“全屏”状态的次数。 | 媒体关闭 | `a.media.states.fullscreen.count` |
| 全屏总时长 | 视频处于“全屏”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.fullscreen.time` |
| 受聚焦影响的流数量 | 如果在播放会话期间发生至少一次聚焦状态，则会触发。 | 媒体关闭 | `a.media.states.infocus.set` |
| 聚焦计数 | 视频进入“聚焦”状态的次数。 | 媒体关闭 | `a.media.states.infocus.count` |
| 聚焦总时长 | 视频处于“聚焦”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.infocus.time` |
| 受静音影响的流数量 | 如果在播放会话期间发生至少一次静音状态，则会触发。 | 媒体关闭 | `a.media.states.mute.set` |
| 静音计数 | 视频进入“静音”状态的次数。 | 媒体关闭 | `a.media.states.mute.count` |
| 静音总时长 | 视频处于“静音”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.mute.time` |
| 受画中画影响的流数量 | 如果在播放会话期间发生至少一次画中画状态，则会触发。 | 媒体关闭 | `a.media.states.pictureinpicture.set` |
| 画中画计数 | 视频进入“画中画”状态的次数。 | 媒体关闭 | `a.media.states.pictureinpicture.count` |
| 画中画总时长 | 视频处于“画中画”状态的时间量（以秒为单位）。 | 媒体关闭 | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
