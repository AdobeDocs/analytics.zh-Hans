---
title: 收入
description: 所有订单中已购买产品的货币金额。
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# 收入

“收入”[量度](overview.md)显示所有订单中购买产品的货币金额。 此量度对于电子商务网站衡量转化率至关重要。 您可以将此量度与任何维度组合，以了解哪些维度项目对收入做出了贡献。 例如，您可以看到热门促销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门内部搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此指标

至于 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 变量中存在 `purchase` 的每次点击，对 [`products`](/help/implement/vars/page-vars/products.md) 变量中的“价格”字段求和。

如果页面上的货币与报表包的原生货币不同，则此度量取决于 [currencyCode](/help/implement/vars/config-vars/currencycode.md) 变量。
