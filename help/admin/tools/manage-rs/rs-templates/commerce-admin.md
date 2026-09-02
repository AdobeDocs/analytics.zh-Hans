---
description: 定义电子商务网站的通用设置。
title: 商务
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
TQID: https://experienceleague.adobe.com/l1-8tv-5dvKi4rx9-2tRoN4hK9ROr-ajWgKm0uFggrI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 58%

---

# 商务

定义电子商务网站的通用设置。

| 转化变量 | 类型 | 子关系 | 分配 | 过期 | `s_code` 变量 |
|---|---|---|---|---|---|
| 内部促销活动 | 字符串 | 基本 | 最近（上一个） | 访问 | `evar1` |
| 内部搜索词 | 字符串 | 基本 | 最近（上一个） | 访问 | `evar2` |
| 促销类别 | 字符串 | 基本 | 最近（上一个） | 访问 | `evar3` |
| Commerce变量4 | 字符串 | 基本 | 最近（上一个） | 访问 | `evar4` |
| Commerce变量5 | 字符串 | 基本 | 最近（上一个） | 访问 | `evar5` |

| 成功事件 | 类型 | `s_code` 变量 |
|---|---|---|
| 注册 | 计数器（无子关系） | `event1` |
| 自定义事件1-5 | 计数器（无子关系） | `event1, event2, event3, event4, event5` |

| 自定义洞察变量 | `s_code` 变量 |
|---|---|
| 流量属性 1-5 | `prop1, prop2, prop3, prop4, prop5` |

下表包含标准商务事件的列表。 这些事件的初始配置在所有报表包模板中都相同。 无需设置s_code变量为N/A的事件，会自动提供这些事件。

| 标准Commerce事件 | 类型 | `s_code` 变量 |
|---|---|---|
| 收入 | 计数器 | `purchase` |
| 订单数 | 计数器 | `purchase` |
| 件数 | 计数器 | `purchase` |
| 购物车 | 计数器 | `scOpen` |
| 购物车查看 | 计数器 | `scView` |
| 实例 | 计数器 | 不适用 |
| 结账 | 计数器 | `scCheckout` |
| 购物车加货 | 计数器 | `scAdd` |
| 购物车减货 | 计数器 | `scRemove` |
| 访问次数 | 计数器（无子关系） | 不适用 |
| 页面查看次数 | 计数器（无子关系） | 不适用 |
| 每日独特访客 | 计数器（无子关系） | 不适用 |
| 独特访客 | 计数器（无子关系） | 不适用 |
