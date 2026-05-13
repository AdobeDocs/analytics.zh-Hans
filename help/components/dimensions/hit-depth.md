---
title: 点击深度
description: 点击进行访问的次数。
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 94%

---

# 点击深度

“点击深度”[维度](overview.md)报告给定点击访问的深度。 此维度对于了解访客在您网站上执行操作的访问深度非常重要。 点击深度计算所有类型的点击，包括页面视图 ([`t()`](/help/implement/vars/functions/t-method.md)) 和链接跟踪点击 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

## 维度项目

维度项目包括字符串 `"Hit Depth"`，后跟一个数字，表示点击进行访问的次数。 维度项目 `"Hit Depth 1"` 表示访问的第一次点击，维度项目 `"Hit Depth 8"` 表示访问的第 8 次点击。

## 与访问深度相比较

点击深度计算所有类型的点击，包括页面视图和链接跟踪点击。 访问深度仅对于页面查看点击进行递增，_且_[页面](page.md)维度项目与上一页的值不同。 访问深度也是一个基于访问的维度，这意味着访问中的所有点击具有相同的值。 下表概述了一个访问示例，以及它如何考虑点击深度 + 访问深度：

| 页面序列 | 点击深度 | 是否计入访问深度？ | 访问深度 |
| --- | --- | --- | --- |
| 主页 | 1 | 是 | 4 |
| 产品页面 | 2 | 是 | 4 |
| 主页 | 3 | 是 | 4 |
| 自定义链接点击 | 4 | 否（自定义链接） | 4 |
| 自定义链接点击 | 5 | 否（自定义链接） | 4 |
| 产品页面 | 6 | 是 | 4 |
| 自定义链接点击 | 7 | 否（自定义链接） | 4 |
| 产品页面 | 8 | 否（与上一页相同） | 4 |
