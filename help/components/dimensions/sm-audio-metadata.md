---
title: 流媒体服务音频元数据维度
description: 为报表包启用[!UICONTROL 音频元数据]时可用的维度。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 8%

---

# 流媒体服务音频元数据维度

流媒体服务和维度通过流媒体服务库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media广告]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[音频元数据](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 |
| --- | --- | --- | --- |
| 专辑 | 专辑的名称。 | 媒体开始，媒体关闭 | `a.media.album` |
| 艺人 | 艺人的姓名。 | 媒体开始，媒体关闭 | `a.media.artist` |
| 作者 | 有声读物作者的姓名。 | 媒体开始，媒体关闭 | `a.media.author` |
| 标签 | 记录标签的名称。 | 媒体开始，媒体关闭 | `a.media.label` |
| 发布者 | 音频内容发布者的名称。 | 媒体开始，媒体关闭 | `a.media.publisher` |
| 电台/电视台 | 无线电台的名称或ID。 | 媒体开始，媒体关闭 | `a.media.station` |

{style="table-layout:auto"}
