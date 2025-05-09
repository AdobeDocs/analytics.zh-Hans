---
description: 用于根据页面事件确定点击类型的查找表。
keywords: 页面；事件；页面事件；post_page_event
title: 页面事件查找
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# 页面事件查找

用于根据`page_event`值确定点击类型的查找表。 如[数据列引用](datafeeds-reference.md)中所述，`page_event`和`post_page_event`列不带正负号的tinyint。

* 请参阅[`t()`](/help/implement/vars/functions/t-method.md)以了解如何为AppMeasurement和Web SDK实施页面查看调用。
* 请参阅[`tl()`](/help/implement/vars/functions/tl-method.md)以了解如何为AppMeasurement和Web SDK实施链接跟踪调用。
* 请参阅[使用Adobe Experience Platform Edge Network实施Adobe Analytics](/help/implement/aep-edge/overview.md)，了解Adobe Analytics如何将XDM负载转换为页面事件类型。

| `page_event` value | `post_page_event` value | 描述 |
| --- | --- | --- |
| `0` | `0` | 所有标准页面查看调用。 它是大多数点击的默认值。 |
| `10` | `100` | 自定义链接。 将链接类型设置为`o` (AppMeasurement)或`xdm.web.webInteraction.type`设置为`other` (Web SDK或移动SDK)。 |
| `11` | `101` | 下载链接。 将链接类型设置为`d` (AppMeasurement)或`xdm.web.webInteraction.type`设置为`download` (Web SDK或移动SDK)。 |
| `12` | `102` | 退出链接。 将链接类型设置为`e` (AppMeasurement)或`xdm.web.webInteraction.type`设置为`exit` (Web SDK或移动SDK)。 |
| `31` | `76` | 媒体开始 |
| `32` | `77` | 媒体更新（无其他变量处理） |
| `33` | `78` | 媒体更新（通过其他变量处理） |
| `40` | `80` | 调查 |
| `50` | `50` | 流媒体开始 |
| `51` | `51` | 流媒体关闭 |
| `52` | `52` | 流媒体推移 |
| `53` | `53` | 流媒体保持活动状态 |
| `54` | `54` | 流媒体广告开始 |
| `55` | `55` | 流媒体广告关闭 |
| `56` | `56` | 流媒体广告推移 |
| `60` | `60` | Primetime媒体开始 |
| `61` | `61` | Primetime媒体关闭 |
| `62` | `62` | Primetime媒体清理 |
| `63` | `63` | Primetime媒体保持活动状态 |
| `64` | `64` | Primetime媒体广告开始 |
| `65` | `65` | Primetime媒体广告关闭 |
| `66` | `66` | Primetime媒体广告推移 |
| `70` | `70` | 包括Target活动数据 |
