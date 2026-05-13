---
description: 用于根据页面事件确定点击类型的查找表。
keywords: page;event;page_event;post_page_event
title: 页面事件查找
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: https://experienceleague.adobe.com/QAGYKNnpMl2tM6BRux7BBL-YFpMTgUIXsHT-9bGKWnA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 100%

---

# 页面事件查找

用于根据 `page_event` 值确定点击类型的查找表。 如[数据列引用](datafeeds-reference.md)中所述，`page_event` 和 `post_page_event` 两列的类型是 tinyint 无符号。

* 请参阅 [`t()`](/help/implement/vars/functions/t-method.md)，了解如何为 AppMeasurement 和 Web SDK 实施页面浏览量调用。
* 请参阅 [`tl()`](/help/implement/vars/functions/tl-method.md)，了解如何为 AppMeasurement 和 Web SDK 实施链接跟踪调用。
* 请参阅[使用 Adobe Experience Platform Edge Network 实施 Adobe Analytics](/help/implement/aep-edge/overview.md)，了解 Adobe Analytics 如何将 XDM 负载转换为页面事件类型。

| `page_event` value | `post_page_event` value | 描述 |
| --- | --- | --- |
| `0` | `0` | 所有标准页面浏览量调用。 这是大多数点击的默认值。 |
| `10` | `100` | 自定义链接。 将链接类型设置为`o`（AppMeasurement）或`xdm.web.webInteraction.type`设置为`other`（Web SDK 或 Mobile SDK）。 |
| `11` | `101` | 下载链接。 将链接类型设置为`d`（AppMeasurement）或`xdm.web.webInteraction.type`设置为`download`（Web SDK 或 Mobile SDK）。 |
| `12` | `102` | 退出链接。 将链接类型设置为`e`（AppMeasurement）或`xdm.web.webInteraction.type`设置为`exit`（Web SDK 或 Mobile SDK）。 |
| `31` | `76` | 媒体开始 |
| `32` | `77` | 媒体更新（无其他变量处理） |
| `33` | `78` | 媒体更新（和其他变量处理） |
| `40` | `80` | 调查 |
| `50` | `50` | 流媒体开始 |
| `51` | `51` | 流媒体关闭 |
| `52` | `52` | 流媒体清理 |
| `53` | `53` | 流媒体保持活动 |
| `54` | `54` | 流媒体广告开始 |
| `55` | `55` | 流媒体广告关闭 |
| `56` | `56` | 流媒体广告清理 |
| `60` | `60` | Primetime 媒体开始 |
| `61` | `61` | Primetime 媒体关闭 |
| `62` | `62` | Primetime 媒体清理 |
| `63` | `63` | Primetime 媒体保持活动状态 |
| `64` | `64` | Primetime 媒体广告开始 |
| `65` | `65` | Primetime 媒体广告关闭 |
| `66` | `66` | Primetime 媒体广告清理 |
| `70` | `70` | 包含 Target 活动数据 |
