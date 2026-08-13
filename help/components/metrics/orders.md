---
title: 订单数
description: 购买的次数。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
TQID: https://experienceleague.adobe.com/jRd-oUTfcJXACj-mkEyzRm8k-rxcVCxe7U3lROIy7DQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 90
ht-degree: 65%

---

# 订单数

“订单数”[量度](overview.md)显示您的网站上发生的购买事件总数。 此量度对于电子商务网站衡量转化率至关重要。 您可以将此量度与任何维度组合，以了解哪些维度项目对订单做出了贡献。 例如，您可以看到促成购买的热门促销活动（使用[跟踪代码](../dimensions/tracking-code.md)维度）或热门搜索词（使用 [eVar](../dimensions/evar.md)）。

## 如何计算此指标

此指标计算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 变量中存在 `purchase` 的点击数。
